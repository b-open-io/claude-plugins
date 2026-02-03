# bOpen Marketplace

Plugin marketplace for Claude Code. BSV blockchain operations, AI tools, and developer utilities.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add b-open-io/claude-plugins
```

Then install any plugin:

```bash
/plugin install <plugin-name>@b-open-io
```

## Plugins

| Plugin | Description | Install |
|--------|-------------|---------|
| [bsv-skills](#bsv-skills) | 24 skills for BSV wallets, identity, transactions, standards | `/plugin install bsv-skills@b-open-io` |
| [1sat-skills](#1sat-skills) | 1Sat Ordinals minting, media extraction, marketplace | `/plugin install 1sat-skills@b-open-io` |
| [bopen-tools](#bopen-tools) | 19 agents, 9 skills, hooks for development workflows | `/plugin install bopen-tools@b-open-io` |
| [gemskills](#gemskills) | Gemini AI image generation, analysis, editing | `/plugin install gemskills@b-open-io` |
| [sigma-auth](#sigma-auth) | Bitcoin-native OAuth with BAP identity | `/plugin install sigma-auth@b-open-io` |
| [clawbook-skills](#clawbook-skills) | On-chain social for AI agents — post, like, follow on BSV | `/plugin install clawbook-skills@b-open-io` |
| [peacock](#peacock) | VSCode theme integration with 24-bit statusline | `/plugin install peacock@b-open-io` |
| [clawnet-bot](#clawnet-bot) | Bot templates and skills for ClawNet AI agent platform | `/plugin install clawnet-bot@b-open-io` |

---

## bsv-skills

BSV blockchain development toolkit.

```bash
/plugin install bsv-skills@b-open-io
```

**Wallet Development**
- `wallet-brc100` - BRC-100 wallet implementation (TypeScript)
- `wallet-brc100-go` - BRC-100 wallet implementation (Go)
- `wallet-send-bsv` - P2PKH transactions with @bsv/sdk
- `wallet-encrypt-decrypt` - ECDH encryption with BSV keys

**Identity & Authentication**
- `create-bap-identity` - BAP identity creation (Type42/Legacy)
- `manage-bap-backup` - Export identities from .bep files
- `encrypt-decrypt-backup` - Encrypted backup management
- `message-signing` - BSM, BRC-77, Sigma signing

**Standards Reference**
- `bsv-standards` - BRCs, BitCom protocols, token standards
- `key-derivation` - Type42, BIP32, BAP derivation patterns
- `ordfs` - ORDFS gateway API

**Script Templates**
- `create-script-template` - Author new ScriptTemplate implementations
- `review-script-template` - Audit templates against best practices

**Mining**
- `stratum-v1` - Stratum v1 protocol (JSON-RPC)
- `stratum-v2` - Stratum v2 binary protocol
- `calculate-mining-difficulty` - Target/bits/difficulty conversion

**On-Chain Data**
- `junglebus` - Real-time transaction streaming
- `bsocial` - On-chain social protocol

**Utilities**
- `check-bsv-price` - Current price from WhatsOnChain
- `decode-bsv-transaction` - Parse transaction hex
- `validate-bsv-script` - Analyze locking/unlocking scripts
- `lookup-bsv-address` - Address balance, history, UTXOs
- `lookup-block-info` - Block data by height or hash
- `estimate-transaction-fee` - Fee calculation

[Documentation](https://github.com/b-open-io/bsv-skills)

---

## 1sat-skills

1Sat Ordinals NFT operations.

```bash
/plugin install 1sat-skills@b-open-io
```

- `extract-blockchain-media` - Extract media from transactions
- `wallet-create-ordinals` - Mint inscriptions
- `ordinals-marketplace` - Browse GorillaPool marketplace

**Requirements:** `txex` CLI, `js-1sat-ord` package

[Documentation](https://github.com/b-open-io/1sat-skills)

---

## bopen-tools

Development workflow automation.

```bash
/plugin install bopen-tools@b-open-io
```

**Agents** (19 specialized sub-agents)

| Agent | Focus |
|-------|-------|
| `prompt-engineer` | Skill and command authoring |
| `code-auditor` | Security and code quality |
| `test-specialist` | Testing strategies |
| `documentation-writer` | Technical writing, PRDs |
| `auth-specialist` | Authentication systems |
| `database-specialist` | Database design |
| `payment-specialist` | Payment integrations |
| `nextjs16-specialist` | Next.js migration |
| `bitcoin-specialist` | BSV blockchain |
| `design-specialist` | UI/UX design |
| `mobile-specialist` | React Native, Swift, Kotlin |
| `devops-specialist` | Deployment, infrastructure |
| `mcp-specialist` | MCP server development |
| `data-specialist` | ETL, analytics |
| `integration-expert` | API integrations |
| `optimizer` | Performance optimization |
| `consolidator` | Code organization |
| `research-specialist` | Information gathering |
| `content-specialist` | AI media generation |

**Skills**
- `npm-publish` - Package publishing workflow
- `resend-integration` - Email with Resend
- `frontend-design` - UI design patterns
- `notebooklm` - Google NotebookLM integration
- `bitcoin-auth-diagnostics` - Auth troubleshooting
- `plaid-integration` - Bank account connections
- `cli-demo-gif` - Terminal recordings with vhs
- `x-research` - X/Twitter research via Grok
- `saas-launch-audit` - Launch readiness checklist

**Hooks**
- Auto git add after edits
- Lint on save/session start
- Environment file protection
- Uncommitted changes reminder

[Documentation](https://github.com/b-open-io/prompts)

---

## gemskills

AI-powered image operations via Google Gemini.

```bash
/plugin install gemskills@b-open-io
```

- `ask-gemini` - Text generation + multi-image analysis
- `generate-image` - Create images with Imagen 3.0
- `upscale-image` - 2x or 4x upscaling
- `edit-image` - Inpainting and outpainting
- `generate-svg` - Scalable vector graphics
- `segment-image` - Object segmentation and masking

**Requirements:** `GEMINI_API_KEY` from [Google AI Studio](https://aistudio.google.com/apikey)

[Documentation](https://github.com/b-open-io/gemskills)

---

## sigma-auth

Bitcoin-native OAuth for Next.js.

```bash
/plugin install sigma-auth@b-open-io
```

- `setup-nextjs` - Integration guide for Next.js
- Bitcoin wallet authentication flow
- BAP identity integration
- OAuth client setup and token exchange

**Requirements:** `SIGMA_MEMBER_PRIVATE_KEY`, registered OAuth client ID

[Documentation](https://github.com/b-open-io/better-auth-plugin)

---

## clawbook-skills

On-chain social network skills for AI agents.

```bash
/plugin install clawbook-skills@b-open-io
```

- `read-feed` - Read posts from global, channel, or user feeds
- `post` - Create posts and replies on-chain
- `like` - Like/unlike posts
- `follow` - Follow/unfollow users
- `setup-identity` - Create BAP identity (local or Sigma Identity)
- `setup-wallet` - Generate and fund BSV wallet

**Requirements:** `bsv-skills` plugin, `sigma-auth` plugin

[Documentation](https://github.com/b-open-io/clawbook-skills)

---

## peacock

VSCode Peacock theme integration with Claude Code statusline.

```bash
/plugin install peacock@b-open-io
```

- Automatic theme detection from `.vscode/settings.json`
- 24-bit true color support
- Project-aware statusline with CWD tracking
- Git branch and lint status display
- iTerm2 tab color matching

After install, run `/peacock:setup` and restart Claude Code.

[Documentation](https://github.com/b-open-io/claude-peacock)

---

## clawnet-bot

Bot templates and skills for the ClawNet AI agent platform.

```bash
/plugin install clawnet-bot@b-open-io
```

**Templates**
- `moltbook` - Moltbook social network integration (default)
- `minimal` - Bare bones HTTP server starter
- `blockchain` - BSV-focused with Bitcoin authentication

**Skills**
- `convex` - Convex database persistence
- `moltbook-example` - Moltbook API client and social tools
- `vercel-blob` - File storage with Vercel Blob

**Usage:**
```bash
# Install skill
bunx skills add b-open-io/clawnet-bot --skill convex

# Use template
clawnet bot init --template moltbook
```

[Documentation](https://github.com/b-open-io/clawnet-bot)

---

## Contributing

Add your plugin to the marketplace:

1. Fork this repository
2. Add entry to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin",
  "source": {
    "source": "url",
    "url": "https://github.com/youruser/your-plugin.git"
  },
  "description": "What your plugin does"
}
```

3. Update this README
4. Submit a pull request

**Requirements:**
- Clear documentation
- `.claude-plugin/plugin.json` manifest
- Tested and working
- No private key exfiltration

---

## Disclaimer

Plugins are provided "as is" under MIT License.

- **Key security:** Never share private keys with AI agents unless in a secure local environment you control
- **Financial risk:** Blockchain transactions are irreversible. Review code before mainnet operations
- **Audit first:** Check plugin permissions before allowing transaction execution

---

## Support

- [GitHub Issues](https://github.com/b-open-io/claude-plugins/issues)
- [GitHub Discussions](https://github.com/b-open-io/claude-plugins/discussions)
- [Claude Code Docs](https://docs.anthropic.com/en/docs/build-with-claude/claude-code)

## License

MIT
