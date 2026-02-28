# tab-marketplace

A curated Claude Code plugins marketplace by AltTab.

## Installation

```
/plugin marketplace add alttab-macbook/tab-marketplace
```

## Available Plugins

*No plugins yet. Add your first plugin to `.claude-plugin/marketplace.json`.*

## Adding a Plugin

To add a plugin to this marketplace, add an entry to the `plugins` array in `.claude-plugin/marketplace.json`:

```json
{
  "name": "my-plugin",
  "source": {
    "source": "url",
    "url": "https://github.com/owner/my-plugin.git"
  },
  "description": "What this plugin does",
  "version": "1.0.0",
  "strict": true
}
```

## License

MIT
