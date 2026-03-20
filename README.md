# SCSS Claude Plugin Marketplace

A community-maintained collection of Claude Code plugins, skills, and MCP servers — built by and for the **SCSS (Second Circuit / Second Soul)** Discord community.

## What's in here?

| Path | Type | Description |
|------|------|-------------|
| `plugins/scss-games` | Plugin | Interactive games and idea-development experiences |

## How to use a plugin

1. Clone this repo (or just the plugin folder you want).
2. Point your Claude Code installation at the plugin directory — see the [Claude Code plugin docs](https://docs.anthropic.com/en/docs/claude-code) for details.
3. The skills, commands, and agents defined in each plugin will become available in your session.

## Repository layout

```
plugins/          Claude Code plugins
  <plugin-name>/
    plugin.json   Plugin manifest
    skills/       Skill .md files
    commands/     Slash commands (if any)
    agents/       Sub-agents (if any)
    hooks/        Hooks (if any)
mcp-servers/      MCP server implementations (coming soon)
```

## Contributing

We love pull requests. If you have a skill, game, command, or MCP server you'd like to share with the SCSS community, open a PR — all experience levels welcome.

Please keep one plugin (or MCP server) per PR to make review easy.

## Community

SCSS — Second Circuit / Second Soul. Find us on Discord.

## Licence

GPL-3.0 — see [LICENSE](LICENSE) for details.
