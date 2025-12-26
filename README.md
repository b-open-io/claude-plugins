# bOpen Marketplace

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![BSV](https://img.shields.io/badge/Blockchain-BSV-e8b315.svg)](https://bsvblockchain.org/)
[![Claude Code](https://img.shields.io/badge/Built%20For-Claude%20Code-d97757.svg)](https://anthropic.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**Supercharging Claude Code for the BSV Blockchain.**

Welcome to the **bOpen Marketplace**, the premier ecosystem for Claude Code plugins dedicated to Bitcoin SV (BSV) development. We bridge the gap between natural language AI and the scalable power of the BSV blockchain, enabling developers to build, deploy, and manage Bitcoin applications with unprecedented speed.

---

## ⚠️ Terms of Service & Disclaimer

**Please read carefully before using any plugins from this marketplace.**

> **Beta Software / Use at Your Own Risk**
> The plugins listed in this repository are community-contributed and provided "AS IS" without warranty of any kind, express or implied.
>
> 1.  **Financial Risk:** These tools interact with the BSV blockchain. Improper use may result in the loss of funds (BSV, Tokens, or Ordinals). Always test on a Testnet (Regtest/Testnet) before using Mainnet funds.
> 2.  **Code Verification:** While we strive for quality, you are responsible for reviewing the code generated or executed by these plugins. Do not blindly execute financial transactions suggested by AI.
> 3.  **Private Keys & Security:** Never share your private keys or backup passphrases. Use the `FLOW_BACKUP_PASSPHRASE` environment variable pattern for encrypted storage.
> 4.  **Affiliation:** This marketplace is an independent community project and is not officially affiliated with Anthropic (Claude) or specific wallet providers unless explicitly stated.

By using the bOpen Marketplace, you agree to these terms and accept full responsibility for your development activities.

---

## 🚀 Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add b-open-io/claude-plugins
```

Then install any plugin:

```bash
/plugin install <plugin-name>@b-open-io
```

---

## 📦 Featured Plugins

Explore our curated suite of tools designed to cover every aspect of the BSV development stack.

### 🔐 BSV Skills
**The Core Foundation.** A comprehensive toolkit for BSV blockchain operations.

**Install:**
```bash
/plugin install bsv-skills@b-open-io
```

**Skills:**
- Backup Management: `encrypt-decrypt-backup`, `create-bap-identity`, `manage-bap-backup`
- Wallet Operations: `wallet-send-bsv`, `wallet-encrypt-decrypt`
- On-Chain Social: `bsocial-posts`
- Utilities: `check-bsv-price`, `decode-bsv-transaction`, `lookup-bsv-address`

**Requirements:** `FLOW_BACKUP_PASSPHRASE` env var, `bbackup` and `bap` CLI tools

[View Documentation →](https://github.com/b-open-io/bsv-skills)

---

### 🎨 1Sat Skills
**Ordinals & NFTs.** Specialized tools for the 1Sat Ordinals protocol.

**Install:**
```bash
/plugin install 1sat-skills@b-open-io
```

**Skills:**
- `extract-blockchain-media` - Extract ordinals from transactions (txex)
- `wallet-create-ordinals` - Mint ordinals/inscriptions
- `ordinals-marketplace` - Browse GorillaPool marketplace

**Requirements:** `txex` CLI (`bun add -g txex`)

[View Documentation →](https://github.com/b-open-io/1sat-skills)

---

### 🔑 Sigma Auth
**Identity & Authentication.** Bitcoin-native OAuth with BAP identity.

**Install:**
```bash
/plugin install sigma-auth@b-open-io
```

**Skills:**
- `setup-nextjs` - Next.js OAuth integration guide

**Features:**
- Better Auth + Sigma Identity integration
- Bitcoin wallet authentication
- BAP identity workflows

[View Documentation →](https://github.com/b-open-io/better-auth-plugin)

---

### 🤖 Gemskills
**AI-Powered Design & Vision.** Gemini 3.0 Pro for design analysis and image operations.

**Install:**
```bash
/plugin install gemskills@b-open-io
```

**Skills:**
- `ask-gemini` - Multi-image analysis (up to 10 images)
- `generate-image`, `upscale-image`, `edit-image`
- `generate-svg`, `segment-image`

**Requirements:** `GEMINI_API_KEY` ([Get API Key](https://aistudio.google.com/apikey))

[View Documentation →](https://github.com/b-open-io/gemskills)

---

### 🔧 Gemcp
**Gemini MCP Server.** Text generation, conversations, and image generation.

**Install:**
```bash
/plugin install gemcp@b-open-io
```

**Features:**
- `gemini_generate` - Text generation with reasoning modes
- `gemini_messages` - Conversation-based generation
- `gemini_image` - Image generation and editing

**Requirements:** `GEMINI_API_KEY`

[View Documentation →](https://github.com/rohenaz/gemcp)

---

### 🦚 Peacock
**Statusline Themes.** Peacock theme integration with 24-bit color support.

**Install:**
```bash
/plugin install peacock@b-open-io
/peacock:setup
```

**Features:**
- Auto-detect Peacock themes from VS Code settings
- 24-bit true color statusline
- Git branch and lint status
- Project-aware CWD tracking

[View Documentation →](https://github.com/b-open-io/claude-peacock)

---

## 🤝 Contributing

We believe in the power of open source and the Metanet. We welcome contributions from all BSV developers!

### How to Contribute
1.  **Fork** the repository
2.  **Create** a feature branch (`git checkout -b feature/amazing-new-plugin`)
3.  **Commit** your changes with clear documentation
4.  **Push** to the branch
5.  **Open a Pull Request**

### Plugin Guidelines
*   **Safety First:** Plugins handling private keys must have strict security warnings
*   **BSV Standards:** Adhere to established BSV standards (derivation paths, script formats)
*   **Documentation:** Every plugin must have a comprehensive README
*   **Testing:** Include test cases and usage examples
*   **Security:** Use environment variables for secrets (`FLOW_BACKUP_PASSPHRASE` pattern)

### Plugin Structure
```
your-plugin/
├── .claude-plugin/
│   └── plugin.json        # Manifest with name, version, components
├── skills/                # Agent skills (optional)
│   └── skill-name/
│       └── SKILL.md       # Skill definition
├── commands/              # Slash commands (optional)
├── agents/                # Custom agents (optional)
└── README.md             # Documentation
```

---

## 💬 Community & Support

Join the bOpen community and connect with other BSV developers.

*   **GitHub Issues:** [Report bugs or request features](https://github.com/b-open-io/claude-plugins/issues)
*   **Discussions:** [Community discussions](https://github.com/b-open-io/claude-plugins/discussions)
*   **BSV Association:** [Learn about Bitcoin SV](https://bsvblockchain.org/)

---

## 📚 Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/build-with-claude/claude-code)
- [Agent SDK Documentation](https://docs.anthropic.com/en/api/agent-sdk)
- [BSV Documentation](https://docs.bsvblockchain.org/)
- [b-open-io GitHub](https://github.com/b-open-io)

---

<p align="center">
  Built with 🧡 for the <b>Bitcoin SV</b> ecosystem.
</p>
