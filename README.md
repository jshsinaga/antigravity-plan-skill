# Antigravity Plan Skill

An agent skill for writing reviewable implementation plans in the Antigravity
`implementation_plan.md` style. It explores the project, describes changes per
file, records decisions and blocking questions, and waits for approval before
editing source files.

## Install

Run from the project where you want to use the skill:

```sh
npx skills add jshsinaga/antigravity-plan-skill --skill antigravity-plan
```

The CLI prompts you to choose your coding agents. Add `-g` to install globally.
Requires Node.js 22.20 or later for the current skills CLI.

To inspect the available skill without installing it:

```sh
npx skills add jshsinaga/antigravity-plan-skill --list
```

## Use

Ask your agent:

```text
Use antigravity-plan to plan adding password reset to this project.
```

The skill also describes automatic triggers for planning requests when your
agent supports skill discovery. Explicitly naming the skill is the most direct
way to select it.

The resulting plan includes:

- A goal description and optional problem background or architecture diagram.
- `User Review Required`, with alerts for decisions and risks.
- `Open Questions`, limited to blocking questions.
- `Proposed Changes`, grouped by component with `[NEW]`, `[MODIFY]`, and
  `[DELETE]` file entries.
- `Verification Plan`, with automated commands and manual checks.

Plans follow the language of your request while preserving the four anchor
headings in English. The agent writes `implementation_plan.md`, or
`docs/plans/<slug>.md` when the project already uses that plans directory, and
waits for your approval. Answer questions or request revisions in the same plan,
then approve implementation.

## Skill source

The complete instructions are in
[`skills/antigravity-plan/SKILL.md`](skills/antigravity-plan/SKILL.md).

For local discovery validation:

```sh
npx skills add . --list
```

This repository contains Markdown instructions, so there is no application build
or typecheck step.

## Directory

Install and discover skills through [skills.sh](https://skills.sh).
According to the [skills.sh publication FAQ](https://skills.sh/docs/faq), skills
are listed through anonymous installation telemetry from the skills CLI. There
is no separate package upload step; directory visibility can lag installation.

## Attribution

An independent, community skill inspired by Google Antigravity's planning
format. This project is not affiliated with or endorsed by Google.

## License

[MIT](LICENSE), copyright (c) 2026 Josua Sinaga.
