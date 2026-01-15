---
name: send-secret-clipboard
version: 0.0.1
description: This skill should be used when the user asks to "send clipboard as secret", "share what I copied", "send my clipboard securely", "share copied text", "share my clipboard", "send what's in my clipboard", or wants to share clipboard contents without the agent seeing them. macOS only - uses pbpaste to pipe clipboard directly to send-secret.
allowed-tools: Bash(pbpaste *), Bash(npx send-secret*)
---

# Send Secret from Clipboard (macOS)

Share clipboard contents as an encrypted secret without the agent ever seeing what was copied. The clipboard is piped directly to send-secret, bypassing the agent's context entirely.

## Security Model

This is one of the safest agentic patterns for secret sharing:

| Action | Safe | Reason |
|--------|------|--------|
| `pbpaste \| send-secret` | Yes | Clipboard bypasses agent context |
| User tells agent the secret | NO | Secret enters conversation context |
| Agent reads from file then pipes | NO | File content enters context |

**Why this works**: The user copies the secret to clipboard manually. The agent runs `pbpaste | send-secret` without ever seeing what's in the clipboard. The piped data goes directly from clipboard to the encryption process.

## Platform Support

| Platform | Command | Available |
|----------|---------|-----------|
| macOS | `pbpaste` | Yes |
| Linux (X11) | `xclip -selection clipboard -o` | Varies |
| Linux (Wayland) | `wl-paste` | Varies |
| Windows | `powershell Get-Clipboard` | Varies |

This skill focuses on macOS. For other platforms, verify the clipboard command exists first.

## Command Reference

```bash
# Basic clipboard send
pbpaste | npx send-secret

# Multiple recipients
pbpaste | npx send-secret -n 3

# With timeout
pbpaste | npx send-secret -t 300

# Combined
pbpaste | npx send-secret -n 5 -t 600
```

## Workflow

1. **Instruct user** to copy their secret to clipboard (Cmd+C)
2. **Confirm** they have copied the secret
3. **Ask** about view count and timeout preferences
4. **Run** `pbpaste | npx send-secret` with options
5. **Provide URL** to user
6. **Inform** to keep terminal open until delivered

## Use Cases

### API key sharing
User: "I need to share an API key with my teammate"

Response:
1. "Copy the API key to your clipboard (Cmd+C)"
2. Wait for confirmation
3. Run: `pbpaste | npx send-secret`
4. Share the URL

### Password sharing
User: "Send my copied password securely"

```bash
pbpaste | npx send-secret -t 120  # 2 minute timeout for passwords
```

### Quick credential sharing
User: "Share what I just copied"

```bash
pbpaste | npx send-secret
```

## Important Notes

- **User must copy first**: The agent cannot access clipboard contents, so user must manually copy
- **Clipboard is transient**: If user copies something else, original secret is lost
- **No file metadata**: Unlike file sends, clipboard sends have no filename - they appear as text secrets
- **Empty clipboard fails**: If clipboard is empty, send-secret will error with "No data to send"

## Verification

To verify clipboard has content (without seeing it):

```bash
pbpaste | wc -c  # Shows byte count, not content
```

If this returns 0, clipboard is empty.

## Error Handling

| Error | Cause | Resolution |
|-------|-------|------------|
| "No data to send" | Clipboard empty | Ask user to copy secret first |
| "pbpaste: command not found" | Not macOS or pbpaste missing | Use file-based send instead |
| Process exits immediately | Clipboard may be binary/incompatible | Use file-based send instead |

## What NOT To Do

```bash
# NEVER ask user to paste in chat
"Paste your secret here"  # WRONG: enters agent context

# NEVER try to read clipboard for verification
pbpaste  # WRONG: would display clipboard to agent

# NEVER echo clipboard
echo $(pbpaste) | send-secret  # WRONG: subshell exposes content
```

## Example Interaction

User: "I need to send my database password to the ops team"

Agent response:
1. "Copy the database password to your clipboard using Cmd+C"
2. "Let me know when you've copied it"

User: "Done"

Agent:
```bash
pbpaste | npx send-secret -n 3 -t 300
```

"Here's your secure link: [URL]. It can be viewed 3 times and expires in 5 minutes. Keep this terminal open until the ops team has retrieved it."
