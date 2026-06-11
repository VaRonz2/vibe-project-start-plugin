---
name: vibe-project-start
description: Prepare an AI-built project before coding by organizing the project workspace, defining the MVP, writing milestones, setting Git checkpoints, establishing AI collaboration roles, and optionally defining a frontend skeleton with design style, UI library, component rules, tokens, i18n, and theme rules. Use when the user wants to start a new app/site/tool, productize an existing prototype, begin vibe coding, avoid chaotic AI-generated code, plan MVP scope, create project kickoff docs, initialize a project folder, set up a Git-based workflow before implementation, or prepare web/app frontend architecture before asking AI to write UI code.
---

# Vibe Project Start

Use this skill to slow down before coding and turn a fuzzy AI-build idea into a controlled project workspace. The goal is to make the next coding session safer: clear folders, clear MVP, clear milestones, clear Git checkpoints, clear roles for AI collaboration, and for frontend projects a stable UI skeleton before AI writes pages.

## Operating Mode

Default to action when the user asks to set up or start a project. Ask at most one clarification question only if the project goal or target folder is genuinely unclear.

If the user only asks for advice, return a concise kickoff plan. If the user asks to "do it", create or update the kickoff artifacts in the project.

For an existing project, inspect the repo first:

```bash
pwd
rg --files -g "!*node_modules*" -g "!*.png" -g "!*.jpg" | head
git status --short
```

On Windows PowerShell, use equivalent commands without destructive actions.

## Workflow

1. Identify the project intent.
   - Target user
   - Core problem
   - Primary platform: web, mobile, desktop, CLI, automation, content workflow, etc.
   - Current state: idea only, rough prototype, existing repo, deployed app
   - User's next deadline or desired first demo

2. Create a project room.
   - Prefer a small `docs/` folder rather than scattering planning files.
   - Do not move user files unless asked.
   - If the repo has existing conventions, follow them.

3. Define the MVP before writing product code.
   - State the single core loop.
   - List "must have", "nice later", and "not now".
   - Name the smallest demo that proves value.
   - Include assumptions and risks that could invalidate the MVP.

4. Write milestones with exit criteria.
   - Each milestone should produce something runnable, inspectable, or testable.
   - Keep milestones small enough that a Git checkpoint makes sense.
   - Add a verification step for each milestone.

5. Set up Git discipline.
   - Always check whether the folder is already a Git repo.
   - If no repo exists and the user asked for setup, initialize Git.
   - Add or update `.gitignore` only for obvious generated/dependency files.
   - Do not commit unrelated existing user changes.
   - Stage only files created or edited for this kickoff.
   - Make a commit only when the user explicitly asks for a commit/checkpoint, or when the task specifically includes setting up Git checkpoints and only kickoff files are staged.

6. Establish AI collaboration roles.
   - Product Manager: clarify user journey, MVP, non-goals, success metrics.
   - Architect: choose architecture, data model, integrations, deployment shape.
   - Developer: implement one milestone at a time.
   - QA: define test cases, edge cases, regression checks.
   - Release Manager: environment variables, deployment, rollback, handoff notes.

7. Add a frontend skeleton when the project includes a web UI, mobile UI, desktop UI, dashboard, landing page, admin panel, or app interface.
   - Define the visual language before generating pages.
   - Choose the frontend framework and UI component library before scaffolding.
   - Set directory, module, and component boundaries.
   - Define design tokens, i18n conventions, and theme rules when relevant.
   - Write these decisions into `docs/FRONTEND_SKELETON.md` as the source of truth.

8. Stop before feature coding unless the user also asked to implement.
   - The output of this skill is a ready-to-code project structure and plan.
   - If implementation is requested in the same turn, start from Milestone 0 or 1, not from random features.

## Kickoff Artifacts

Create these files when setting up a project unless the repo already has equivalent docs:

- `docs/PROJECT_BRIEF.md`
- `docs/MVP.md`
- `docs/MILESTONES.md`
- `docs/AI_RULES.md`

Optional files:

- `.gitignore` when missing or clearly incomplete
- `docs/FRONTEND_SKELETON.md` for web, mobile, desktop, or app UI projects
- `docs/DECISIONS.md` for architecture decisions in larger projects
- `docs/RELEASE_CHECKLIST.md` when the project is intended for public users

## Frontend Skeleton

Use this branch only when the project has a meaningful UI. The purpose is to prevent AI-generated frontend code from drifting across pages.

Before asking AI to build UI pages, define:

- Overall design style: visual language, color direction, typography, type scale, line height, spacing, radius, elevation, card style, button shape, layout density, and navigation model.
- Frontend technical plan: framework, routing, state management, data fetching, form handling, validation, icons, charting, testing, and build tool.
- UI component library: pick a mature library or local design system when possible; explain how custom components should wrap it.
- Directory rules: where pages/routes, components, features, hooks, utilities, API clients, styles, assets, and tests live.
- Module boundaries: what each feature owns and what must stay shared.
- Component reuse rules: naming, props, variants, composition, when to create a reusable component, and when to keep UI local.
- Style system: design tokens for colors, spacing, radii, shadows, typography, z-index, breakpoints, and motion.
- i18n rules when the product may support multiple languages: message storage, key naming, formatting, fallback language, and no hard-coded user-facing strings.
- Theme rules when the product may support light/dark or branded variants: token mapping, semantic colors, and contrast checks.
- Skeleton acceptance checks: first screen renders, responsive layout works, no text overlap, basic navigation works, and components follow the source-of-truth document.

For frontend projects, M1 should usually become "Runnable Frontend Skeleton" rather than generic "Runnable Skeleton".

## File Templates

Use compact templates. Replace placeholders with project-specific content.

### docs/PROJECT_BRIEF.md

```markdown
# Project Brief

## Goal
[One paragraph explaining what this project helps users do.]

## Target Users
- [Primary user]
- [Secondary user, if any]

## Core Problem
[The pain or job-to-be-done.]

## Core Loop
1. [User enters/collects/chooses something]
2. [System processes/saves/recommends something]
3. [User gets a useful output or takes an action]

## Success Metric
- [Observable sign that the MVP works]

## Non-Goals
- [What this project will not do yet]
```

### docs/MVP.md

```markdown
# MVP

## MVP Statement
[The smallest version that proves the product is useful.]

## Must Have
- [Required capability]

## Nice Later
- [Deferred capability]

## Not Now
- [Explicitly excluded capability]

## Assumptions
- [Assumption to validate]

## Risks
- [Risk and how to reduce it]
```

### docs/MILESTONES.md

```markdown
# Milestones

## M0 - Project Room
Goal: Make the project understandable before coding.
Exit Criteria:
- Project brief exists
- MVP scope exists
- Git status is known
Verification:
- Read docs back and confirm they match the user goal

## M1 - Runnable Skeleton
Goal: Create the smallest runnable app or workflow.
Exit Criteria:
- App/workflow starts locally
- No placeholder flow blocks the core loop
Verification:
- Run the local start command or smoke test

## M2 - MVP Core Loop
Goal: Complete the main user journey.
Exit Criteria:
- User can complete the core loop end to end
- Data is saved or exported where needed
Verification:
- Manual walkthrough plus focused tests

## M3 - Shareable Version
Goal: Prepare for another person to try it.
Exit Criteria:
- Basic error states handled
- Setup instructions or deployment path exists
- Release checklist is complete
Verification:
- Fresh-run test from a clean state
```

### docs/AI_RULES.md

```markdown
# AI Collaboration Rules

## Roles
- Product Manager: keep scope small and user-centered.
- Architect: protect structure, data flow, and integration boundaries.
- Developer: implement one milestone at a time.
- QA: test the core loop and edge cases.
- Release Manager: prepare handoff, deployment, and rollback notes.

## Working Rules
- Do not start feature coding before checking MVP and milestones.
- Prefer small changes with a verification step.
- Keep generated files out of Git unless they are intended source artifacts.
- Do not rewrite unrelated code while completing a milestone.
- Record major architecture decisions in `docs/DECISIONS.md` when they affect future work.

## Prompt Pattern
Before coding, ask the AI to respond in this order:
1. Product reading: what user problem are we solving?
2. Scope boundary: what is MVP vs later?
3. Technical plan: what files and modules change?
4. Verification: how will we know it works?
5. Git checkpoint: what should be committed after success?
```

### docs/FRONTEND_SKELETON.md

```markdown
# Frontend Skeleton

## Purpose
[Explain what UI this project needs and what the first usable screen should accomplish.]

## Design Style
- Visual language: [quiet/productive/playful/editorial/etc.]
- Color direction: [primary, neutrals, semantic colors]
- Typography: [font choices or system font, size scale, line height]
- Spacing and radius: [spacing scale, border radius rules]
- Layout density: [compact/comfortable/data-dense]
- Navigation model: [top nav/sidebar/tabs/bottom nav/etc.]

## Frontend Stack
- Framework: [React/Next.js/Vue/etc.]
- Routing: [choice]
- State: [choice]
- Data fetching/API: [choice]
- Forms and validation: [choice]
- Icons: [choice]
- Tests: [choice]

## UI Component Library
- Library: [choice]
- Usage rule: [wrap library components locally or use directly]
- Custom components: [when to create them]

## Directory Rules
- `src/app-or-routes/`
- `src/components/`
- `src/features/`
- `src/hooks/`
- `src/lib/`
- `src/styles/`
- `src/assets/`
- `src/tests/`

## Module Boundaries
- `features/[name]` owns feature-specific UI, data mapping, and local state.
- `components/` contains reusable, domain-neutral components.
- `lib/` contains shared clients, utilities, and adapters.
- Pages/routes compose features and handle layout-level concerns.

## Component Rules
- Prefer composition over large configurable components.
- Create variants only when at least two real usages need them.
- Keep feature-specific text and behavior out of shared components.
- Name components by user-facing role, not implementation detail.

## Design Tokens
- Colors: [semantic token names]
- Spacing: [scale]
- Radius: [scale]
- Typography: [scale]
- Shadows/elevation: [scale]
- Breakpoints: [rules]
- Motion: [duration/easing rules]

## i18n Rules
- Store user-facing strings in [location].
- Use stable keys: `[feature].[surface].[message]`.
- Keep date, number, and currency formatting centralized.
- Avoid hard-coded user-facing strings in components.

## Theme Rules
- Use semantic tokens, not raw colors, inside components.
- Check contrast for light/dark variants.
- Keep brand-specific overrides in one theme file.

## Skeleton Acceptance Checks
- App starts locally.
- First screen renders without broken layout.
- Navigation skeleton exists.
- Responsive desktop/mobile frames are usable.
- No text overlaps or overflows obvious containers.
- Shared components follow this document.
```

## Quality Bar

Before finishing, verify:

- The artifacts match the actual project, not generic boilerplate.
- The MVP is small enough to build in one or two focused sessions.
- Each milestone has observable exit criteria.
- Frontend projects have a single source of truth for visual style, stack, component rules, tokens, i18n, and themes before UI generation.
- Git status is reported accurately.
- No unrelated files were changed.

In the final response, summarize the created/updated files, the MVP, the next milestone, whether a frontend skeleton was added, and whether a Git repo/checkpoint was created.
