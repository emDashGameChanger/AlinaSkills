# AlinaSkills

Claude Code skills for the BioMedBound / biolab drug-repurposing project.
This directory is cloned directly to `~/.claude/skills/` on the project
machine so the skills apply globally, and is pushed to
`emDashGameChanger/AlinaSkills` on GitHub as the source of truth.

## AI use & transparency

This project uses Claude Code extensively — docking workflow scaffolding,
website updates, research documentation, and more — and that should never be
hidden or downplayed. Be transparent about it: in commit messages, in
lab-notebook entries, and in any write-up of results or website content,
note where AI tooling did the work.

Part of the point of this project is the question itself: how far does
current AI let us go? If Alina can run 3 miles on her own, and a bike lets
her ride 30, the bike is the interesting thing to write about, not something
to hide. Her understanding, decisions, and hands-on lab work drive the
science — Claude Code extends reach, it doesn't ghostwrite the runner's
effort out of the story. Don't scrub AI involvement out of posts, notes, or
history to make the work look more "manual" than it is.

## Skills

- **docking-run** — run a standardized fpocket + AutoDock-Vina-GPU docking
  pass and log results reproducibly.
- **website-tutorial-page** — add/edit a BioMedBound page consistent with
  existing nav, styling, and voice.
- **target-research** — research and document a candidate rare/under-studied
  disease target before docking.
- **lab-notebook** — maintain a dated project log of runs and decisions.

See each skill's `SKILL.md` for details. Project-specific conventions these
skills assume (repo layout, hardware, style guide) live in the
`AlinaWebsite` repo's `CLAUDE.md`.
