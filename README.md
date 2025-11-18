# b-open-io Claude Code Plugins

> Official plugin marketplace for b-open-io Claude Code extensions

This marketplace provides curated plugins for Claude Code that enhance your development workflow.

## Installation

Add this marketplace to Claude Code:

```shell
/plugin marketplace add b-open-io/claude-plugins
```

## Available Plugins

### 🎨 Peacock

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
