---
name: target-research
description: Research and document a candidate rare or under-studied disease target for drug-repurposing docking. Use when selecting or evaluating a disease target, protein structure, or FDA-approved drug candidate list before running docking experiments.
---

# Target research

Help pick and document a disease target for the drug-repurposing project
before docking work starts. This is a research/documentation step, not a
docking-execution step (see the `docking-run` skill for that).

## What makes a good candidate target

- A rare or under-studied disease with real unmet treatment need — prefer
  conditions that don't already have heavy pharmaceutical R&D focus (that's
  where drug repurposing is most likely to matter).
- A druggable protein target implicated in the disease, with an available
  3D structure: prefer a solved crystal/cryo-EM structure (PDB), fall back
  to a high-confidence predicted structure (AlphaFold DB) if no experimental
  structure exists — note explicitly which case applies.
- A binding site that's plausible to dock against (known active/allosteric
  site, or one fpocket identifies as high-druggability).

## Sourcing an FDA-approved drug candidate list

- Use a recognized source for the approved-drug library (e.g. DrugBank's
  approved-drug set, ZINC15's "FDA approved" subset, or another clearly
  identified source) — don't hand-assemble an ad hoc list without recording
  where it came from.
- Record the source name, version/date pulled, and how many compounds it
  contains. Libraries drift over time — reproducibility depends on knowing
  exactly which snapshot was used.

## Documenting findings

Write findings to `biolab/targets/<target-name>.md`, not just chat output,
so the work is reusable and can feed both future docking runs and website
tutorial content. Include:
- Disease and why it was chosen (rarity/under-studied status, unmet need)
- Target protein, its role in the disease, and evidence for druggability
- Structure source (PDB ID, or AlphaFold + confidence notes) and how it was
  obtained
- Candidate drug library: source, version/date, size
- Open questions / what still needs verification before committing to a full
  docking campaign

## Scope note

This is hypothesis-generation, not a clinical or medical claim. Always frame
target selection and candidate rationale as "worth investigating
computationally," not as an established therapeutic finding.
