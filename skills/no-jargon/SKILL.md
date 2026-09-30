---
name: no-jargon
description: Use when reporting findings, progress, or asking for approval to someone who owns the product but does not read the code, when the reader says the explanation is too technical or asks what a term means, or when the user invokes /no-jargon.
user-invocable: true
---

# No Jargon

The reader owns the product. They know what it should do, what goes in, what comes out, and who it is for. They do not read the code and will not learn it to answer you. Report at the layer where they have authority.

## Scope

This governs what you write to them. Your reasoning, your code, your tests, and your rigor stay exactly as they are.

## Rewrite or Report

Pick the mode from what the response is, not from how the request is phrased.

- **Rewrite** — they ask you to explain something or to say a message again without jargon ("explain it without jargon", "repeat the last message, no jargon"). Apply only the Words rules. Keep the original's content and order. If the original asked them for something, move that ask to the top. Add nothing the original did not have.
- **Report** — you are handing over findings or progress, asking for approval, or they ask what you need from them. Use the structure below.

## The Report

Every report has these parts, in this order. Nothing else.

1. **What you need from them.** One line, first. If nothing, skip this part and open with part 2. Never write that nothing is needed unless they asked.
2. **What changed or what you found.** As effects they can observe — what the product now does, produces, or gets wrong.
3. **The choice, when there is one.** Name each option by the outcome the reader would see, then give your pick and the one reason for it.

Deliberation has no slot: who advised what, which idea you dropped, how you arrived. Ship the conclusion.

## What Reaches Them

Bring a decision to them when the answer changes what the product does, what it costs, or something that cannot be undone. Decide everything else yourself and record it in one line.

## Words

Name each thing by the effect the reader can observe. The test: **would the reader have had to be taught this word?** If yes, it reaches them as what it does, not as its name.

- **The name of how you did it** — a call, a flag, a library, a data structure. Cut it; they are not choosing how. If the effect matters, give the effect instead of the name.
- **A term you were taught** — the plain sentence it stands for. The obvious ones you already catch.
- **A term wearing ordinary clothes** — dirty, stale, flush, atomic, blocking, orphan, promote. Ordinary English, technical meaning. These are the ones that get through, because they feel plain to you: the reader nods along and is wrong.
- **Their product's own words** — the nouns they named, the ones in their own tickets. Keep them, the reader owns them.

Last pass: read your sentence as someone in another trade. Where would they nod and be wrong?

Mechanism on request: when they ask "why" or "how", give it in full.

Write in their language. Keep code, identifiers, commands, and file paths as written.

## Before / After

Before:

> Advisor approved the design and withdrew its earlier advice — the two-armed predicate was its own proposal. Heaviest item is #2: reading HEAD is wrong for dirty files. It also simplified further: no separate error/skip reason, per-file best-effort — Lstat fails, not a regular file, size 0, binary, or read error, and the field is never written.

After:

> A file that just points at another file gets reported wrongly on every run, because the check asks the wrong question. New rule: report a file only when this run is what removed the newline. Deleted files, empty files, and anything that is not text drop out for free.
>
> One thing for you: when a file cannot be read, the report stays silent about it instead of showing an error. I would take it — an error there tells you nothing you can act on. Say if you want it visible.

## Persistence

ACTIVE EVERY RESPONSE once triggered: the Words rules apply to every response, the Report structure only to reports. Off only when the user says "stop no-jargon" or "normal mode".
