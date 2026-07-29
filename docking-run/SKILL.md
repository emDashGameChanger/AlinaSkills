---
name: docking-run
description: Run a standardized fpocket + AutoDock-Vina-GPU docking pass and log the results reproducibly. Use whenever running or repeating a molecular docking experiment for the BioMedBound / biolab project.
---

# Docking run

Standardize how docking experiments are run and recorded so every run is
reproducible and can be turned into tutorial content or lab-notebook entries
later.

## Before starting

- Confirm the receptor identity (PDB ID) and ligand identity (PubChem CID,
  SMILES, or other clear source) with the user if not already given.
- Confirm the `biolab` conda env is set up (`conda env list`); if not, point
  to `biolab/setup.sh`.
- Activate it: `conda activate biolab`.

## Pocket detection (if pocket-guided)

- Run `fpocket` on the receptor PDB if binding-site detection is needed.
- Review the resulting `<receptor>_info.txt` and pick a pocket by druggability
  score / volume / relevance to the known or hypothesized binding site.
- Record which pocket ID was chosen and why (druggability score, volume, or
  match to a known binding site).

## Docking

- Prepare/convert files with Open Babel as needed (`.sdf`/`.pdb` → `.pdbqt`).
- Write or update `config.txt` with receptor/ligand paths and the box
  center/size derived from the chosen pocket (or known binding site) plus a
  reasonable `search_depth`.
- Run: `./AutoDock-Vina-GPU-2-1 --config config.txt`, capturing full stdout
  to a log file (don't let it just print to the terminal and get lost).

## Recording results

Save everything for one run together, under a descriptive subfolder, e.g.
`biolab/runs/<receptor>-<ligand>-<short-description>/`:
- `config.txt` used
- full Vina log
- `receptor.pdbqt`, `ligand.pdbqt` (or references to shared/reused files)
- `output.pdbqt` (docked poses)
- a short `NOTES.md`: receptor + ligand identity, pocket used (if any) and
  why, resulting best affinity score(s), anything unusual

## Wrap-up

- Summarize the best affinity score(s) for the user.
- Flag anomalies: non-convergence, box too small/large for the pocket,
  binding mode that looks physically implausible.
- Suggest a `lab-notebook` entry for the run.
