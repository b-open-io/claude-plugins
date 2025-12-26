# bOpen Marketplace

Official plugin marketplace for Claude Code - BSV blockchain operations, AI tools, and developer utilities.

> **⚖️ Terms of Service & Disclaimer**
>
> **Please read before using:** The plugins in the bOpen Marketplace are provided "as is" under the MIT License.
> - **You are responsible for your keys:** Never share private keys with an AI agent unless you are running it in a secure, local environment you control.
> - **Financial Risk:** These tools interact with the BSV blockchain. Transactions are irreversible. **b-open-io** is not responsible for lost funds, failed transactions, or unintended contract interactions.
> - **Audit First:** Always review the code or plugin permissions before allowing Claude to execute transactions on mainnet.

## Welcome to the bOpen Marketplace

Supercharge your development workflow by bridging the gap between Natural Language and the BSV Blockchain. The **bOpen Marketplace** is the premier directory for **Claude Code** plugins, designed to give your AI agent direct capability to interact with Bitcoin SV.

Whether you need to mint Ordinals, authenticate users via Bitcoin, or generate UI components on the fly, our curated collection of plugins turns Claude into a full-stack blockchain developer. Stop writing boilerplate and start building the future of the internet.

## Quick Start

Add this marketplace to Claude Code:

```bash
/plugin marketplace add b-open-io/claude-plugins
```

Then install any plugin:

```bash
/plugin install <plugin-name>@b-open-io
```

## Available Plugins

| Plugin | Category | Description | Install |
|--------|----------|-------------|---------|
| **[bsv-skills](#bsv-skills)** | 🔗 Blockchain | 11 skills for BSV operations, BRC-100 wallets (TS/Go), BAP identity, BSocial | `/plugin install bsv-skills@b-open-io` |
| **[1sat-skills](#1sat-skills)** | 🎨 NFTs | 3 skills for 1Sat Ordinals, media extraction, marketplace | `/plugin install 1sat-skills@b-open-io` |
| **[gemskills](#gemskills)** | 🤖 AI/Design | 6 skills for Gemini AI image generation, analysis, editing | `/plugin install gemskills@b-open-io` |
| **[sigma-auth](#sigma-auth)** | 🔐 Auth | Bitcoin-native OAuth for Next.js with BAP identity | `/plugin install sigma-auth@b-open-io` |
| **[gemcp](#gemcp)** | 🤖 AI/Design | Gemini MCP server for text/image generation | `/plugin install gemcp@b-open-io` |
| **[peacock](#peacock)** | 🛠️ Dev Tools | Theme integration with 24-bit color statusline | `/plugin install peacock@b-open-io` |

---

## The Marketplace

### 🔗 BSV & Blockchain Operations

*Core tools for wallet management, transaction building, and network interaction.*

#### bsv-skills

**11 comprehensive skills for BSV blockchain development**

- `wallet-brc100` - **NEW** BRC-100 wallet development (TypeScript - @bsv/wallet-toolbox)
- `wallet-brc100-go` - **NEW** BRC-100 wallet development (Go - go-wallet-toolbox)
- `encrypt-decrypt-backup` - Secure .bep backup management with bitcoin-backup CLI
- `create-bap-identity` - Generate BAP identities (Type42/Legacy) for Bitcoin attestation
- `manage-bap-backup` - List and export BAP member identities
- `wallet-send-bsv` - Send BSV transactions with @bsv/sdk
- `wallet-encrypt-decrypt` - ECDH message encryption with BSV keys
- `bsocial-posts` - Create and read on-chain social media posts (BSocial/BMAP)
- `check-bsv-price` - Get current BSV price from WhatsOnChain API
- `decode-bsv-transaction` - Decode transaction hex into readable format
- `lookup-bsv-address` - Query address balance, history, and UTXOs

**Install:**
```bash
/plugin install bsv-skills@b-open-io
```

**Requirements:** `FLOW_BACKUP_PASSPHRASE`, CLI tools: `bbackup`, `bap`

[View Documentation →](https://github.com/b-open-io/bsv-skills)

---

### 🎨 NFTs & Ordinals

*1Sat Ordinals operations for NFT minting and marketplace browsing.*

#### 1sat-skills

**3 skills for 1Sat Ordinals NFT operations**

- `extract-blockchain-media` - Extract media files from blockchain transactions with txex
- `wallet-create-ordinals` - Mint new ordinals/inscriptions on BSV
- `ordinals-marketplace` - Browse and search GorillaPool marketplace

**Install:**
```bash
/plugin install 1sat-skills@b-open-io
```

**Requirements:** `txex` CLI, `js-1sat-ord` package

[View Documentation →](https://github.com/b-open-io/1sat-skills)

---

### 🤖 AI & Design Tools

*Generative tools powered by Google Gemini for design and visual operations.*

#### gemskills

**6 skills for AI-powered design and image operations**

- `ask-gemini` - Text generation + multi-image analysis (up to 10 images)
- `generate-image` - Create images with Imagen 3.0
- `upscale-image` - Upscale images 2x or 4x
- `edit-image` - Inpainting and outpainting operations
- `generate-svg` - Create scalable SVG graphics
- `segment-image` - Object segmentation and masking

**Install:**
```bash
/plugin install gemskills@b-open-io
```

**Requirements:** `GEMINI_API_KEY` from [Google AI Studio](https://aistudio.google.com/apikey)

[View Documentation →](https://github.com/b-open-io/gemskills)

---

#### gemcp

**Gemini API MCP server for text generation, conversations, and image operations**

- `gemini_generate` - Text generation with thinking/reasoning modes
- `gemini_messages` - Conversation-based generation
- `gemini_image` - Image generation and editing

**Install:**
```bash
/plugin install gemcp@b-open-io
```

**Requirements:** `GEMINI_API_KEY`

[View Documentation →](https://github.com/rohenaz/gemcp)

---

### 🔐 Bitcoin Authentication

*Bitcoin-native authentication with BAP identity support.*

#### sigma-auth

**Bitcoin-native OAuth integration for Next.js applications**

- `setup-nextjs` - Complete guide for integrating Sigma Auth with Next.js
- Bitcoin wallet authentication flow
- BAP (Bitcoin Attestation Protocol) identity integration
- OAuth client setup and token exchange

**Install:**
```bash
/plugin install sigma-auth@b-open-io
```

**Requirements:** `SIGMA_MEMBER_PRIVATE_KEY`, registered OAuth client ID

[View Documentation →](https://github.com/b-open-io/better-auth-plugin)

---

### 🛠️ Developer Utilities

*Tools for enhancing your development environment.*

#### peacock

**Peacock theme integration with 24-bit true color statusline**

- Automatic theme detection from `.vscode/settings.json`
- Project-aware statusline with CWD tracking
- Git branch and lint status
- Theme-matched colors

**Install:**
```bash
/plugin install peacock@b-open-io
/peacock:setup
```

[View Documentation →](https://github.com/b-open-io/claude-peacock)

---

## 🚀 Contributing

**Join the bOpen Ecosystem**

We are building an open ecosystem and we want your tools! If you have built a Claude Code plugin that helps BSV developers:

1. **Fork** this repository
2. **Add** your plugin to `.claude-plugin/marketplace.json`
3. **Update** this README with your plugin details
4. Submit a **Pull Request**

**Plugin Requirements:**
- Well-documented with clear usage instructions
- Follows Claude Code plugin structure
- Includes `.claude-plugin/plugin.json` manifest
- Tested and working
- **Security review:** Plugins must not exfiltrate private keys

### Example Plugin Entry

```json
{
  "name": "your-plugin",
  "source": {
    "source": "url",
    "url": "https://github.com/yourusername/your-plugin.git"
  },
  "description": "Clear description of what your plugin does"
}
```

## Support & Community

- **Issues:** [GitHub Issues](https://github.com/b-open-io/claude-plugins/issues)
- **Discussions:** [GitHub Discussions](https://github.com/b-open-io/claude-plugins/discussions)
- **Documentation:** [Claude Code Docs](https://docs.anthropic.com/en/docs/build-with-claude/claude-code)

## License

MIT License - see individual plugins for their licenses.

---

**Built with ❤️ by the bOpen community for BSV developers**
