# SCSS Plugin Marketplace Scaffold Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Turn the bare repo into a Claude plugin marketplace with a `scss-games` plugin containing the `idea-forge` skill, a comprehensive `.gitignore`, and a welcoming `README.md`.

**Architecture:** Standard Claude plugin layout under `plugins/<name>/` with a `plugin.json` manifest and a `skills/` subdirectory. The existing `idea-forge.md` is moved (not copied) into the plugin. Root-level files (`.gitignore`, `README.md`) handle repo-wide concerns.

**Tech Stack:** Markdown, JSON — no code to compile or test.

---

### Task 1: Create plugin directory structure and move idea-forge.md

**Files:**
- Create: `plugins/scss-games/skills/idea-forge.md` (moved from `idea-forge.md`)

- [ ] **Step 1: Create the directory**

```bash
mkdir -p plugins/scss-games/skills
```

- [ ] **Step 2: Move idea-forge.md into the plugin**

```bash
git mv idea-forge.md plugins/scss-games/skills/idea-forge.md
```

- [ ] **Step 3: Verify the move**

```bash
git status
```

Expected: `renamed: idea-forge.md -> plugins/scss-games/skills/idea-forge.md`

---

### Task 2: Create plugin.json manifest

**Files:**
- Create: `plugins/scss-games/plugin.json`

- [ ] **Step 1: Write plugin.json**

```json
{
  "name": "scss-games",
  "version": "1.0.0",
  "description": "Interactive games and skill experiences for the SCSS (Second Circuit / Second Soul) Discord community.",
  "author": "SCSS Community",
  "skills": [
    "skills/idea-forge.md"
  ]
}
```

- [ ] **Step 2: Verify JSON is valid**

```bash
python3 -m json.tool plugins/scss-games/plugin.json
```

Expected: pretty-printed JSON with no errors.

---

### Task 3: Create .gitignore

**Files:**
- Create: `.gitignore`

- [ ] **Step 1: Write .gitignore covering Python/uv, Node/React, and MCP artefacts**

```gitignore
# Python / uv
__pycache__/
*.py[cod]
*.pyo
.venv/
venv/
.python-version
*.egg-info/
dist/
build/
.cache/

# uv — lock file is intentionally committed, but ignore local overrides
.uv/

# Node / React / npm / pnpm
node_modules/
.next/
out/
.nuxt/
.output/
.pnpm-store/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
*.local

# MCP servers — runtime artefacts
.mcp/
mcp-server/dist/
mcp-server/build/
*.mcp.log

# Environment
.env
.env.local
.env.*.local
.envrc.local

# OS
.DS_Store
Thumbs.db

# Editors
.idea/
*.swp
*.swo
.vscode/settings.json
```

---

### Task 4: Rewrite README.md

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Replace README.md with marketplace introduction**

```markdown
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
```

---

### Task 5: Create GPL-3.0 LICENSE file

**Files:**
- Create: `LICENSE`

- [ ] **Step 1: Download the GPL-3.0 licence text**

```bash
curl -s https://www.gnu.org/licenses/gpl-3.0.txt -o LICENSE
```

Alternatively, copy the full GPL-3.0 text from https://www.gnu.org/licenses/gpl-3.0.txt manually.

- [ ] **Step 2: Verify the file exists and looks correct**

```bash
head -3 LICENSE
```

Expected: starts with `GNU GENERAL PUBLIC LICENSE`

---

### Task 6: Commit everything

- [ ] **Step 1: Stage all new and modified files**

```bash
git add plugins/ .gitignore README.md LICENSE
```

- [ ] **Step 2: Verify staged files look correct**

```bash
git status
```

Expected: staged changes include the renamed `idea-forge.md`, new `plugin.json`, new `.gitignore`, modified `README.md`, and new `LICENSE`.

- [ ] **Step 3: Commit**

```bash
git commit -m "Scaffold SCSS plugin marketplace with scss-games plugin"
```
