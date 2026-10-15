# PROJECT.md

Per-project facts. Fill this in once per project; update it when stack, commands, or structure change.
Agents read it first and must not guess what is missing. Write `none` or `TBD` instead of leaving a field blank.
Name frameworks but not exact versions; the lockfile/manifest is the source of truth for versions.

## Overview
- Name:
- One-line purpose:
- Target user:
- Stage: (prototype / in use / production)

## Tech Stack & Dependencies
- Language(s) / runtime:
- Framework(s):
- Database / storage:
- Hosting / deploy:
- Dependency manifest(s): (e.g. package.json, go.mod, pom.xml, requirements.txt, Cargo.toml)
## Commands (exact, from repo root; write `none` if it does not exist yet)
- Install:
- Dev server:
- Format:
- Lint:
- Typecheck:
- Test (all):
- Test (single file):
- Build:
- DB migrate / seed:

## Structure (annotated tree)
```text
/
├── src/            # what lives here
│   ├── ...
├── tests/          # where tests live
└── ...
```
## Documentation & Knowledge Base (Internal)
> *This registry adapts to each project. Add domain-specific rows as needed (e.g. `docs/runbooks/` for DevOps, `docs/experiments/` for ML, `docs/compliance/` for Fintech) or write `none` if a category does not apply.*

| Type | Path / Location | Purpose |
|---|---|---|
| Architecture / ADR | `docs/adr/` or `docs/architecture/` | Technical decisions & trade-offs |
| Specs / Features | `docs/specs/` or `docs/features/` | Feature specifications & acceptance criteria |
| API Contract | `docs/api/` or `openapi.yaml` | Endpoints, payloads, and protocols |
| Database Schema | `prisma/schema.prisma` or `migrations/` or `db/schema.sql` | Source of truth for database models |

## External Project Management & Design (External Tools)
- PRD / Wiki (Notion, Confluence):
- UI/UX Design (Figma, Miro):
- Issue Tracker / Board (Jira, Linear, GitHub Issues, Trello):

## Planning & Tracking
- Milestones / Backlog: `ROADMAP.md` or `TODO.md`
- Release history: `CHANGELOG.md`
- Agent active tasks: `.agents/tasks/`

## Key files
| File | Purpose |
|---|---|
| | |

## Conventions
- Naming (files, functions, components, constants):
- Error handling pattern:
- State / data-fetching pattern:
- Styling / UI library:
- Other project-specific rules (e.g. all UI strings go through i18n):

## Environment variables (names only, never values)
| Name | Required? | Purpose |
|---|---|---|
| | | |

## Common tasks
Step-by-step recipes for work that repeats in this project. Example:

### Add a new page
1.
2.
3.

### Add a new API endpoint
1.
2.
3.

### Change the database schema
1.
2.
3.

## Constraints and gotchas
- Must not touch:
- Known quirks:

## Non-goals
-
