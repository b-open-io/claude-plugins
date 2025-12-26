# b-open-io Claude Code Plugins

> Official plugin marketplace for b-open-io Claude Code extensions

This marketplace provides curated plugins for Claude Code that enhance your development workflow.

## Installation

Add this marketplace to Claude Code:

```shell
/plugin marketplace add b-open-io/claude-plugins
```

## Available Plugins

### Peacock

Peacock theme integration for Claude Code - statusline with 24-bit true color support.

**Install:**
```shell
/plugin install peacock@b-open-io
/peacock:setup
# Restart Claude Code
```

**Uninstall:**
```shell
/peacock:unsetup
/plugin  # Select peacock and uninstall
```

**Features:**
- Automatic Peacock theme detection from `.vscode/settings.json`
- 24-bit true color for exact hex color matching
- Project-aware statusline with CWD and edited project tracking
- Git branch and lint status with theme-matched colors
- `/project-color` command for setting workspace colors

[View Documentation →](https://github.com/b-open-io/claude-peacock)

---

### Gemcp

Google Gemini API MCP server - text generation, conversations, and image generation/editing.

**Install:**
```shell
/plugin install gemcp@b-open-io
# Set your API key in environment: GEMINI_API_KEY
# Restart Claude Code
```

**Features:**
- `gemini_generate` - Text generation with thinking/reasoning modes
- `gemini_messages` - Conversation-based generation
- `gemini_image` - Image generation and editing (pass `input_image` for editing)

**Requirements:**
- `GEMINI_API_KEY` environment variable - Get from [Google AI Studio](https://aistudio.google.com/apikey)

[View Documentation →](https://github.com/rohenaz/gemcp)

---

### Gemskills

Gemini 3.0 Pro Preview skills for design analysis, image generation, and visual operations.

**Install:**
```shell
/plugin install gemskills@b-open-io
# Set your API key in environment: GEMINI_API_KEY
```

**Skills:**
- `ask-gemini` - Text generation and multi-image analysis (up to 10 images)
- `generate-image` - Image generation with imagen-3.0
- `upscale-image` - Upscale images 2x or 4x
- `edit-image` - Inpainting and outpainting
- `generate-svg` - SVG graphics generation
- `segment-image` - Object segmentation and masking

**Features:**
- Gemini 3.0 Pro Preview for spatial awareness and design analysis
- Multi-image support (compare up to 10 images in one request)
- Comprehensive image operations (generate, upscale, edit, segment)
- SVG generation for scalable graphics

**Requirements:**
- `GEMINI_API_KEY` environment variable - Get from [Google AI Studio](https://aistudio.google.com/apikey)

[View Documentation →](https://github.com/b-open-io/gemskills)

---

### BSV Skills

Core BSV blockchain operations for Claude Code.

**Install:**
```shell
/plugin install bsv-skills@b-open-io
# Set FLOW_BACKUP_PASSPHRASE environment variable
# Install CLIs: bbackup, bap (see plugin README)
```

**Skills:**
- `encrypt-decrypt-backup` - Encrypt/decrypt .bep backup files
- `create-bap-identity` - Create BAP identities (Type42/Legacy)
- `manage-bap-backup` - List and export BAP members
- `wallet-send-bsv` - Send BSV transactions
- `wallet-encrypt-decrypt` - ECDH message encryption
- `bsocial-posts` - On-chain social media posts
- `check-bsv-price` - BSV price from WhatsOnChain
- `decode-bsv-transaction` - Decode transaction hex
- `lookup-bsv-address` - Address balance and history

**Features:**
- Follows Flow's BSV convention (`/.flow/.bsv/`)
- Encrypted backup management
- BAP identity creation and management
- Wallet operations with @bsv/sdk
- BSocial protocol integration
- WhatsOnChain API utilities

**Requirements:**
- `FLOW_BACKUP_PASSPHRASE` environment variable
- `bbackup` CLI: `bun add -g bitcoin-backup`
- `bap` CLI: Clone and build from github.com/b-open-io/bap-cli

[View Documentation →](https://github.com/b-open-io/bsv-skills)

---

### 1Sat Skills

1Sat Ordinals NFT operations for BSV blockchain.

**Install:**
```shell
/plugin install 1sat-skills@b-open-io
# Install txex: bun add -g txex
```

**Skills:**
- `extract-blockchain-media` - Extract ordinals/media from transactions (txex)
- `wallet-create-ordinals` - Mint new ordinals/NFTs (js-1sat-ord)
- `ordinals-marketplace` - Browse/search GorillaPool marketplace

**Features:**
- Extract inscribed media from blockchain
- Mint ordinals and NFTs
- Search and browse marketplace
- GorillaPool Ordinals API integration

**Requirements:**
- `txex` CLI: `bun add -g txex`
- `js-1sat-ord` package for minting

[View Documentation →](https://github.com/b-open-io/1sat-skills)

---

## Usage

### Install a Plugin

```shell
/plugin install <plugin-name>@b-open-io
```

### Browse Available Plugins

```shell
/plugin
```

Select "Browse Plugins" to see all available options.

### Manage Installed Plugins

```shell
/plugin
```

Select "Manage Plugins" to enable, disable, or uninstall plugins.

## Plugin Development

Want to contribute a plugin to this marketplace?

1. **Create your plugin** following the [Claude Code plugin guide](https://docs.claude.ai/code/plugins)
2. **Test locally** with a development marketplace
3. **Submit a PR** adding your plugin to `marketplace.json`
4. **Include documentation** in your plugin's README

### Plugin Requirements

- Well-documented with clear usage instructions
- Follows Claude Code plugin structure
- Includes versioned `plugin.json` manifest
- Tested and working

### Example Plugin Structure

```
your-plugin/
├── .claude-plugin/
│   └── plugin.json
├── commands/          # Slash commands (optional)
├── agents/           # Custom agents (optional)
├── hooks/            # Event handlers (optional)
├── skills/           # Agent Skills (optional)
└── README.md
```

## Marketplace Structure

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json    # Plugin registry
└── README.md              # This file
```

## Support

- **Issues**: [GitHub Issues](https://github.com/b-open-io/claude-plugins/issues)
- **Discussions**: [GitHub Discussions](https://github.com/b-open-io/claude-plugins/discussions)

## License

MIT License - see individual plugins for their licenses.

## See Also

- [Claude Code Documentation](https://docs.claude.ai/code)
- [Plugin Development Guide](https://docs.claude.ai/code/plugins)
- [b-open-io GitHub](https://github.com/b-open-io)
