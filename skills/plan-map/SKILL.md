---
name: plan-map
description: Use when presenting an implementation plan, a migration, a refactor, a roadmap, or any multi-step change to someone who decides whether it runs but will not read a long document, or when the user invokes /plan-map.
user-invocable: true
---

# Plan Map

A plan gets read once, by someone deciding whether to let it run. The map takes the place of the document for that decision. The detail stays in the document — the map points at it, it never copies it.

**The test: if the reader still has to open the plan to decide, the map failed.**

## What You Produce

Both, every time:

1. **In the conversation: ten lines at most.** What gets built, in what order, what you need from them. Then the path to the map.
2. **One HTML file.** Copy `template.html` from this skill's directory and fill it in. Never write your own CSS and never edit the stylesheet — the template owns how it looks, you own what it says.

If the plan is a straight line of five steps or fewer, it has no shape worth drawing. Say it in five lines and write no file.

## What the Map Must Answer

Five questions, on its own. Each has a place in the template. If any of them sends the reader to the document, the map is not finished.

| Question | Where it goes |
|---|---|
| What will exist when this is done? | the boxes |
| In what order, and what runs at the same time? | the phases |
| How much work is this? | the count on each phase, the totals in the footer |
| What could go wrong? | **Most likely to be wrong** |
| What do you need from me? | **Your call** |
| What is this *not* going to do? | **Not in this plan** |

## Filling the Template

**Lede**: one sentence, what the reader gets when this is done. Anything you learned that does not fit in one sentence belongs in a list below, not here.

**Phases** run left to right, in the order they happen. A phase ends in something the reader would recognise as progress. Use as many as the work has — a large plan may need seven — and no more than the work has.

**Boxes** are things that exist when the work is done: a running service, a screen, a migrated table, a deleted module. Boxes stacked in one phase run at the same time; that is information, use it.

**Every box earns its place by changing the decision.** Delete a box: if the reader would still answer the same way, it was detail — merge it into its neighbour. This, not a box limit, is what keeps the map readable. A map that does not fit on one screen is a map still carrying boxes that do not change the answer.

**Name a box by what the product gains, not by the files it touches.** `Reminder scheduler` — not `scheduler.py + policies.py + recurrence.py`. A label that reads like a file list means you drew the implementer's checklist.

**Counts are counted, never estimated.** Read them off the plan: tasks, steps, verification gates. Never convert them to hours or days — you do not know how long anything takes, and a made-up number is worse than no number.

**`class="risk"`** marks the one box in a phase you would check first. At most one per phase.

**Your call**: decisions that block work until the reader answers, each written as a question. An empty list means you have not found the real decisions; a full one means you have not made your own.

**Most likely to be wrong**: the assumptions you would test first, each with what breaks if it does not hold.

**Not in this plan**: what someone would reasonably assume is included and is not. Pull it from the plan's non-goals, constraints and explicit exclusions.

**Footer**: totals, then the absolute path to the plan document.

## Rules

- Order phases by dependency, not by the order you thought of them.
- Write in the reader's language. Keep code, identifiers, commands and file paths as written.
- A map with nothing marked risky is a plan nobody stress-tested.
- Do not restate steps, commands or verification procedure. That is what the document is for.

## Naming

Write the file next to the plan document it maps, named after the work: `retry-backoff.plan.html`.
