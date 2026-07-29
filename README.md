# AlinaSkills

Claude Code skills for the BioMedBound / biolab drug-repurposing project.
This directory is cloned directly to `~/.claude/skills/` on the project
machine so the skills apply globally, and is pushed to
`emDashGameChanger/AlinaSkills` on GitHub as the source of truth.

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
