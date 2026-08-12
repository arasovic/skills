---
name: session-handoff
description: Use when the user asks for a handoff or continuation prompt, when work must continue in a new session, or when the context window is running low.
user-invocable: true
---

# Session Handoff

Generate a detailed, copy-paste-ready prompt that captures the full state of the current session so work can continue seamlessly in a new conversation.

## Process

1. Analyze the entire conversation to extract:
   - **Project**: Which project/repo is being worked on, key file paths
   - **Task**: What was the original goal/request
   - **Completed**: What has been done so far (files created, modified, deleted; commands run; decisions made)
   - **Current state**: Where things stand right now (what's working, what's broken, what's mid-progress)
   - **Decisions & findings**: Important architectural decisions, rejected alternatives, discovered constraints
   - **Next steps**: What remains to be done, in priority order
   - **Blockers**: Any unresolved issues, questions, or dependencies

2. Output the prompt inside a single fenced code block (```markdown) so the user can copy it easily.

## Output Format

The generated prompt MUST follow this exact structure:

```markdown
## Context
[Include the project name, repo path, tech stack, original goal, and other context needed to continue. Skip this section only when no project context applies.]

## What Was Done
[Bulleted list of completed work with specific file paths and line numbers where relevant]

## Current State
[What's working, what's broken, what's in-progress — be specific]

## Key Decisions
[Important decisions made during this session and WHY, rejected alternatives]

## Next Steps
[Ordered list of remaining work, most important first]

## Blockers / Open Questions
[Any unresolved issues — skip section if none]

## Key Files
[List of files that are most relevant to continue the work]
```

## Rules

- Be SPECIFIC — include file paths, function names, error messages, line numbers
- Include the WHY behind decisions, not just the WHAT
- Next steps should be actionable, not vague ("implement X in Y file" not "continue working")
- If the project has an authoritative task tracker, reference it
- Keep it dense but complete — someone reading only this prompt should be able to continue without any other context
- Match the user's language while preserving code, identifiers, commands, and technical terms as written
- Do NOT include generic context the model already knows (framework docs, language basics)
- Do NOT include the conversation history itself — only the distilled state
