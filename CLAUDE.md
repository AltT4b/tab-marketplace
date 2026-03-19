# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is **tab-marketplace**, a curated Claude Code plugins marketplace by AltTab. It serves as both a registry and the home for Claude Code plugins. Each plugin is a self-contained project living in its own subdirectory under `plugins/`.

## Repository Structure

```
tab-marketplace/
├── .claude-plugin/
│   └── marketplace.json   # Registry index — references plugins in the plugins/ directory
├── plugins/
│   └── <plugin-name>/     # Each plugin is a self-contained project
│       ├── README.md       # Plugin-specific docs
│       └── ...             # Plugin's own codebase, config, etc.
├── CLAUDE.md
├── README.md
└── LICENSE
```

- `.claude-plugin/marketplace.json` — The marketplace index. Contains marketplace metadata and a `plugins` array that references each plugin. This is the registry, not the plugins themselves.
- `plugins/` — Each subdirectory is a complete, self-contained plugin with its own version, README, and codebase.
- `README.md` — Installation instructions and plugin submission guide.
- `LICENSE` — MIT license.

## How It Works

Users install this marketplace into Claude Code with:
```
/plugin marketplace add AltT4b/tab-marketplace
```

Each plugin lives in `plugins/<plugin-name>/` as a self-contained project. The `marketplace.json` file serves as the index that lists and references all available plugins.

## Making Changes

### Adding a new plugin

1. Create a new subdirectory under `plugins/` with the plugin name.
2. Include all plugin code, config, and a README.md within that subdirectory.
3. Add a corresponding entry to the `plugins` array in `.claude-plugin/marketplace.json`.

### Modifying marketplace.json

When editing `.claude-plugin/marketplace.json`, ensure:
- The JSON remains valid
- Each plugin entry has all required fields (`name`, `source`, `description`, `version`, `strict`)
- The `source.url` points to a valid git repository
- Version strings follow semver

### Plugin conventions

- Each plugin is self-contained — all of its code, docs, and config live within its own `plugins/<name>/` directory.
- Each plugin should have its own README.md describing what it does and how to use it.
- Each plugin manages its own versioning independently.

## Commit Patterns

Use [Conventional Commits](https://www.conventionalcommits.org/):

| Pattern | When to use | Example |
|---------|-------------|---------|
| `feat: <msg>` | Adding a new plugin or feature | `feat: add code-review plugin` |
| `fix: <msg>` | Bug fixes in plugins or the marketplace index | `fix: correct source path for tab plugin` |
| `docs: <msg>` | Documentation-only changes | `docs: update installation instructions` |
| `chore: <msg>` | Maintenance, config, or tooling | `chore: update marketplace metadata version` |
| `refactor: <msg>` | Restructuring without behavior change | `refactor: reorganize tab plugin directory layout` |

Use scope for plugin-specific changes:

```
feat(tab): add researcher specialist
fix(tab): correct memory file path
```
