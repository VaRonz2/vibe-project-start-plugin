# Vibe Project Start

Vibe Project Start is a Codex plugin that helps prepare AI-built projects before coding starts.

It gives Codex a lightweight kickoff workflow for:

- Defining the project brief and core user loop
- Scoping the MVP before feature coding
- Writing milestone exit criteria
- Setting Git checkpoint discipline
- Establishing AI collaboration roles
- Preparing an optional frontend skeleton for web/app projects

The bundled skill is `vibe-project-start`.

## When to use it

Use this plugin when you want to start a new app, site, tool, or AI-coded project, or when you want to productize an existing prototype without letting AI-generated code drift.

Example prompt:

```text
Use $vibe-project-start to prepare this project before writing code: define the MVP, milestones, folder structure, Git checkpoints, frontend skeleton, and AI collaboration roles.
```

## What it creates

For a project kickoff, the skill can create or update:

- `docs/PROJECT_BRIEF.md`
- `docs/MVP.md`
- `docs/MILESTONES.md`
- `docs/AI_RULES.md`
- `docs/FRONTEND_SKELETON.md` for projects with a meaningful UI

## Install

Add this repository as a Codex plugin marketplace:

```bash
codex plugin marketplace add <owner>/vibe-project-start-plugin
```

Then open the plugin directory and install **Vibe Project Start** from the marketplace.

If you are testing from a local clone:

```bash
codex plugin marketplace add .
```

## Plugin structure

```text
.agents/plugins/marketplace.json
plugins/vibe-project-start-plugin/.codex-plugin/plugin.json
plugins/vibe-project-start-plugin/skills/vibe-project-start/SKILL.md
```

## License

MIT
