# tab-marketplace

A curated Claude Code plugins marketplace by AltTab.

## Installation

```
/plugin marketplace add AltT4b/tab-marketplace
```

## Available Plugins

| Plugin | Description | Version |
|--------|-------------|---------|
| [tab](plugins/tab) | A thinking partner defined entirely in markdown. No compiled code, no dependencies — just text files that shape how Claude talks, thinks, and works with you. | 0.0.1 |

## Adding a Plugin

To add a plugin to this marketplace:

1. Create a directory under `plugins/` with your plugin's code and a README.
2. Add an entry to the `plugins` array in `.claude-plugin/marketplace.json`:

```json
{
  "name": "my-plugin",
  "source": "./plugins/my-plugin",
  "description": "What this plugin does",
  "version": "1.0.0",
  "strict": true
}
```

For plugins hosted externally:

```json
{
  "name": "my-plugin",
  "source": {
    "type": "url",
    "url": "https://github.com/owner/my-plugin.git"
  },
  "description": "What this plugin does",
  "version": "1.0.0",
  "strict": true
}
```

## License

MIT
