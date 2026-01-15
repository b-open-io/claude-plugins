---
name: send-secret-file
version: 0.0.1
description: This skill should be used when the user asks to "send a secret file", "share a file securely", "share credentials file", "send API keys file", "share .env securely", "encrypt and share file", "send config to teammate", "share SSH key", "send private key file", "share certificate file", or needs to share any sensitive file via P2P encrypted link. The file is encrypted locally and served via a one-time Cloudflare tunnel link.
allowed-tools: Bash(npx send-secret*), Bash(test *), Bash(ls *)
---

# Send Secret File

Share files securely using P2P encrypted links. Files are encrypted locally with AES-256-GCM and served via a temporary Cloudflare tunnel. The decryption key is embedded in the URL fragment (never sent to servers).

## Security Model for Agentic Use

**Critical constraint**: The agent must NEVER read or display file contents.

| Action | Safe | Reason |
|--------|------|--------|
| `send-secret ./file.json` | Yes | File path only, content encrypted by CLI |
| `cat file \| send-secret` | NO | Piping exposes content to agent's context |
| `Read` tool on file | NO | Would load secret into agent's context |
| `echo "$VAR" \| send-secret` | NO | Variable value exposed to agent |

## Command Reference

```bash
# Basic file send (single recipient, no timeout)
npx send-secret <filepath>

# Multiple recipients
npx send-secret -n <count> <filepath>

# Auto-destruct timeout (seconds)
npx send-secret -t <seconds> <filepath>

# Combined: 3 views OR 5 minutes, whichever first
npx send-secret -n 3 -t 300 <filepath>
```

## Workflow

1. **Verify file exists** (use `test -f` or `ls`, never `cat` or `Read`)
2. **Confirm options** with user:
   - How many people need access? (default: 1)
   - Should it expire? (default: no timeout)
3. **Run command** with file path argument
4. **Extract and provide URL** from output to user
5. **Inform user** to keep terminal open until recipient retrieves

## Output Parsing

The CLI outputs a boxed URL like:
```
╭ Share this link ─────────────────────────╮
│ https://xyz.trycloudflare.com/s/abc#key=... │
╰──────────────────────────────────────────╯
```

Extract the full URL including the `#key=...` fragment. The fragment contains the decryption key and is essential.

## Process Lifecycle

The send-secret process runs interactively:
- Stays alive waiting for recipient(s)
- Shows progress: `Waiting for receiver... (0/3)`
- Shows retrieval: `Retrieved (1/3) from 73.162.45.99`
- Exits when all views used or timeout reached
- Can be cancelled with Ctrl+C

**Important**: The process must stay running until delivery completes. Run in foreground, not background.

## Common Scenarios

### Single recipient, no timeout
```bash
npx send-secret ./credentials.json
```

### Team onboarding (multiple people)
```bash
npx send-secret -n 5 ./team-secrets.env
```

### Time-sensitive sharing
```bash
npx send-secret -t 300 ./temp-access.json  # 5 minute window
```

### High security (limited views + timeout)
```bash
npx send-secret -n 2 -t 120 ./api-keys.txt  # 2 views max, 2 min timeout
```

## Error Handling

| Error | Resolution |
|-------|------------|
| "File too large (max 100MB)" | File exceeds size limit |
| "No data to send" | Empty file or path doesn't exist |
| "Tunnel failed" | Network issue, retry or check connection |
| Process killed before retrieval | Recipient needs new link |

## What NOT To Do

```bash
# NEVER pipe file contents
cat secret.json | npx send-secret  # WRONG: agent sees content

# NEVER read file first
Read secret.json, then send  # WRONG: agent sees content

# NEVER echo secrets
echo "sk_live_xxx" | npx send-secret  # WRONG: agent sees secret
```
