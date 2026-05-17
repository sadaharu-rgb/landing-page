# Landing Page Project

## Project Overview

Landing page project. This file provides persistent context for Claude Code.

## Workflow

### Start Every Session

1. **Plan first** — Use plan mode (`/plan`) before implementation. Never code without a plan.
2. **Clarify ambiguity** — Ask before starting if requirements are unclear.
3. **Context management** — Run `/compact` when context reaches ~50% to avoid the "agent dumb zone."

### Development

- Keep PRs small (~100 lines, one feature per PR)
- Commit at least hourly; one commit per feature
- Always squash merge for clean linear history
- Use `/rewind` (Esc Esc) to undo when Claude goes off-track — do not correct inline

## Git Practices

```
feat: add hero section
fix: correct mobile nav overflow
style: adjust CTA button spacing
```

- Small, focused commits per feature
- Descriptive commit messages
- Never bundle unrelated changes

## Code Standards

- No speculative abstractions — solve the current problem only
- No backward-compatibility hacks for removed code
- No error handling for impossible scenarios
- Validate only at system boundaries (user input, external APIs)

## Self-Serve Setup

Any developer launching Claude should be able to run the project successfully on first attempt. If setup fails, this CLAUDE.md is incomplete — update it.

<important if="adding new dependencies">
Document the install command and purpose here so the next developer doesn't need to investigate.
</important>

<important if="debugging">
- Share screenshots when stuck — visual context speeds up diagnosis
- Use background task logging to capture console output
- Run `/doctor` to diagnose Claude Code configuration issues
</important>

## Commands

Store project-specific slash commands in `.claude/commands/` and version-control them.
Repeat daily tasks (more than once/day) → convert to a command.

## Stack

- Framework: None (vanilla HTML only)
- Styling: Vanilla CSS (no preprocessors, no frameworks)
- Deploy: TBD

No build step required. Open `index.html` directly in a browser to develop.
