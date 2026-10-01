# Skills

A curated collection of agent skills I use across projects.

## Install

### Install one skill

For example, install only `no-jargon`:

```sh
npx skills add arasovic/skills --skill no-jargon -g
```

Replace `no-jargon` with any skill name below. Each skill also has its own copyable install command.

### Choose skills interactively

```sh
npx skills add arasovic/skills -g
```

Choose the skills you want during installation.

- **Across projects:** Keep `-g` to install at user level. Omit it to install in the current project.
- **Specific agent:** Append `--agent claude-code` or `--agent codex` to target that agent.

See the [skills CLI documentation](https://github.com/vercel-labs/skills#options) for more installation options.

## Available skills

Use the example prompts below in your agent after installing the skill.

### [no-jargon](./skills/no-jargon/SKILL.md)

Use when an explanation is too technical or a product owner needs a clear report. Explains outcomes, choices, and required decisions in plain language.

```sh
npx skills add arasovic/skills --skill no-jargon -g
```

**Example prompt**

> Use no-jargon. Explain what changed, what it means for users, and what you need from me.

Stays active until you say `stop no-jargon` or `normal mode`.

### [zoom-out](./skills/zoom-out/SKILL.md)

Use when the agent gets stuck in implementation details or follows a narrow approach. Reassesses the goal, assumptions, and wider context, then recommends continuing or changing direction. Works for coding, planning, research, and decisions.

```sh
npx skills add arasovic/skills --skill zoom-out -g
```

**Example prompt**

> Zoom out. Are we solving the right problem? What are we overlooking?

### [plan-map](./skills/plan-map/SKILL.md)

Use when a plan is too long to assess at a glance. Produces an HTML map of the work, dependencies, risks, and decisions. Short, linear plans stay in text.

```sh
npx skills add arasovic/skills --skill plan-map -g
```

**Example prompt**

> Use plan-map. Turn this plan into a visual overview showing dependencies, risks, and decisions I need to make.

### [session-handoff](./skills/session-handoff/SKILL.md)

Use when work needs to continue in a fresh conversation. Produces a copyable continuation prompt with the task, completed work, decisions, current state, and next steps, with sensitive values redacted.

```sh
npx skills add arasovic/skills --skill session-handoff -g
```

**Example prompt**

> Use session-handoff. Write a continuation prompt for a new conversation, including what is done, what remains, and why we made the key decisions.

## License

MIT
