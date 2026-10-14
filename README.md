# Glazeen Skills

> Agent skills maintained by [Glazeen](https://glazeen.ai), opinionated guidance that AI coding agents load while they work.

[![skills.sh](https://skills.sh/b/Glazeen/skills)](https://skills.sh/Glazeen/skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Works with **Claude Code**, **Cursor**, **Codex**, **Windsurf**, **GitHub Copilot**, and 30+ other agents through [skills.sh](https://skills.sh/).

---

## 📦 Available Skills

| Skill | Description |
| --- | --- |
| [`quindici-right-feeling-ui`](skills/quindici-right-feeling-ui/SKILL.md) | UI/UX design laws, mobile viewport budgets, spacing rules, anti-patterns, and component hierarchy for React / Next.js / Tailwind frontends. |

---

## ⚡ Installation

```bash
# List every skill in this repo
npx skills add Glazeen/skills --list

# Pick skills interactively
npx skills add Glazeen/skills

# Install one specific skill
npx skills add Glazeen/skills --skill quindici-right-feeling-ui

# Install every skill
npx skills add Glazeen/skills --skill '*'
```

### Options

| Flag | Purpose |
| --- | --- |
| `-g`, `--global` | Install into your user directory (available in every project) |
| `-a`, `--agent <agent>` | Target specific agents, e.g. `claude-code`, `cursor`, `codex` |
| `-s`, `--skill <name>` | Install only the named skill(s) |
| `-y`, `--yes` | Skip confirmation prompts |

```bash
# Example: one skill, globally, for Claude Code only
npx skills add Glazeen/skills --skill quindici-right-feeling-ui -g -a claude-code
```

---

## 🧩 Skills

### Quindici Right Feeling UI

AI agents tend to default to generic, cluttered dashboards with nested borders, duplicated counters, and bloated mobile headers. This skill loads strict spatial and interaction heuristics into the agent's context whenever it generates or modifies frontend code:

1. **Interaction Archetype Alignment:** classifies every view as a *Visceral Canvas*, an *Operational Console*, or a *Focused Tunnel*, and never mixes them.
2. **Viewport Overhead Budget:** keeps headers under 30% of the mobile viewport, merges metadata into a single inline row, and compresses headers on scroll.
3. **The Law of the Single Anchor:** each metric appears once, no CTA competes with a FAB or dock, and empty states point to the primary trigger.
4. **Spatial Physics & Dock Clearance:** adds safe-area scroll padding, puts scrims behind floating elements, and allows no orphan floating buttons.
5. **Surface Hygiene & State Coherence:** removes nested boxes, hides controls on empty lists, locks the lexicon, and keeps badges off until active.

Before presenting code, the agent checks it against a pre-flight checklist. → [Read the skill](skills/quindici-right-feeling-ui/SKILL.md)

---

## 🗂️ Repository Structure

```
skills/
└── <skill-name>/
    ├── SKILL.md        # required: frontmatter + instructions
    ├── references/     # optional: extra docs loaded on demand
    ├── scripts/        # optional: helper scripts the skill can run
    └── assets/         # optional: templates, images, etc.
```

Each folder under `skills/` is one self-contained skill. The folder name must match the `name` field in its `SKILL.md`.

> ⚠️ Don't put a `SKILL.md` at the repository root. The CLI would treat the whole repo as a single skill, and the skills under `skills/` would be hidden.

---

## ➕ Adding a New Skill

1. Create `skills/<skill-name>/SKILL.md`. Use lowercase, hyphenated names:

   ```markdown
   ---
   name: <skill-name>
   description: "What the skill does and exactly when the agent should use it."
   ---

   # Title

   Instructions for the agent…
   ```

2. Write the `description` carefully. Agents read it to decide when to load the skill, so name the concrete triggers (frameworks, file types, tasks).
3. Add a row to the [Available Skills](#-available-skills) table and a short section under [Skills](#-skills).
4. Check that the CLI finds it:

   ```bash
   npx skills add . --list
   ```

---

## 📄 License

[MIT](LICENSE) © Glazeen.ai
