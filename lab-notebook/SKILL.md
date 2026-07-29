---
name: lab-notebook
description: Maintain a dated lab-notebook log of docking runs, decisions, and results. Use after any docking run, target-research decision, or other notable project milestone to keep a running project record.
---

# Lab notebook

Keep a running, dated record of what was tried, why, and what happened —
separate from per-run detail files, so there's a single place to read the
project's history chronologically.

## Where entries go

- Append to `biolab/labnotebook.md` for project-level entries (target chosen,
  decision made, summary of a docking session).
- Per-run detail already lives in `biolab/runs/<run>/NOTES.md` (see
  `docking-run` skill) — the lab notebook entry for a run should be a short
  summary that links/refers to that folder, not a duplicate of the full
  detail.

## Entry format

Each entry: a date heading, then a short factual paragraph or bullet list.
Keep entries short and reusable — written so they could be lifted almost
directly into a tutorial blog post later. Example shape:

```markdown
## 2026-07-29

Set up biolab/ as a proper repo with reproducible setup.sh. No docking runs
yet — next step is picking a disease target (see target-research skill).
```

## Cross-referencing

- Link to the relevant `biolab/runs/<run>/` folder for docking sessions.
- Link to the relevant `biolab/targets/<name>.md` for target-research
  decisions.
- If an entry's content is substantial enough to become a tutorial page,
  note that as a follow-up (see `website-tutorial-page` skill).

## When to add an entry

After any docking run, any target-research decision, or any other choice
that shapes the direction of the project (e.g. switching tools, hitting and
resolving a setup problem worth remembering). Don't log routine/no-decision
work.
