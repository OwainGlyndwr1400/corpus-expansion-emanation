# Structural Invariance Under Corpus Expansion

## Proclus and Ishraqi Illuminationism Confirm Topology-Family Stability in Emanation Hierarchies

**Erydir Ceisiwr** — Independent Researcher, Awen Grid Programme, Swansea, Wales, UK
ORCID: [0009-0004-4577-5253](https://orcid.org/0009-0004-4577-5253)

> **Zenodo:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19305988.svg)](https://doi.org/10.5281/zenodo.19305988)
> Companion repository to the paper submitted to *Digital Scholarship in the Humanities* (Oxford University Press).
> Extends the computational methodology of [Ceisiwr (2026a)](https://github.com/OwainGlyndwr1400/emanation-topology) from 9 to 11 encoded traditions.

---

## Overview

This repository contains all code, data, and outputs for **WP 1.2** of the Awen Grid Empirical Programme — a corpus expansion study adding two new cosmological traditions to the computational graph-theoretic comparison of emanation hierarchies:

1. **Proclus, *Elements of Theology*** (5th c. CE) — Dodds (1933/1963) edition
2. **Suhrawardi, *Hikmat al-Ishraq*** (12th c. CE) — Walbridge & Ziai (1999) translation

The full pipeline (encoding → invariants → null models → statistics → isomorphism → figures) is re-executed on the expanded 11-schema corpus.

### Key Findings

| Finding | Result |
|---|---|
| Linear chain frequency | 8/11 (72.7%), p < 0.001 |
| Corpus depth vs. null | Mann-Whitney U=8031, p=0.003 |
| Exact structural isomorphisms (GED=0) | 5 (up from 2 in WP 1.1) |
| Ishraq ↔ Samkhya WL similarity | 1.0000 (perfect — 12th-c. Islamic / 4th-c. Indian) |
| Proclus ↔ Plotinus GED | 6.0 (same lineage, divergent structure) |
| Proclus ↔ Sethian GED | 0.0 (opposed theologies, identical structure) |
| Family separation ratio | 2.48x (stable from 2.46x in WP 1.1) |

---

## Repository Structure

```
.
├── data/
│   └── schemas/          # 11 tradition schemas as labelled DAGs (JSON)
├── scripts/              # 6-step computational pipeline (Python 3.11+)
├── outputs/
│   ├── figures/          # 6 publication-ready figures (300 dpi PNG)
│   ├── invariants/       # Topological metrics + statistical results (JSON)
│   └── similarity_matrix/ # Pairwise GED, WL, Levenshtein matrices
├── notes/                # Encoding rationale, scouting reports
├── requirements.txt
└── README.md
```

---

## Reproducing the Results

```bash
# Clone and install
git clone https://github.com/OwainGlyndwr1400/corpus-expansion-emanation
cd corpus-expansion-emanation
pip install -r requirements.txt

# Run the full pipeline
python scripts/run_pipeline.py

# Resume from a specific step
python scripts/run_pipeline.py --from 5

# Run only one step
python scripts/run_pipeline.py --only 6
```

**Runtime:** ~115 seconds on a standard laptop (step 5, isomorphism tests, dominates).
**Python:** 3.11+ required.

---

## The 11 Traditions

| Tradition | Nodes | Depth | Shape | Source |
|---|---|---|---|---|
| Plotinian Neoplatonic | 5 | 4 | Linear chain | Plotinus, *Enneads* |
| Proclan Neoplatonic *(new)* | 8 | 7 | Linear chain | Proclus, *Elements of Theology* (Dodds 1963) |
| Sethian Gnostic | 8 | 7 | Linear chain | Nag Hammadi *Apocryphon of John* |
| Valentinian Gnostic | 9 | 7 | Branching tree | Nag Hammadi, Irenaeus |
| Hermetic | 8 | 3 | Branching tree | *Corpus Hermeticum* I (Poimandres) |
| Chaldean Oracles | 6 | 5 | Linear chain | Majercik (1989) |
| Lurianic Kabbalistic | 7 | 6 | Linear chain | Vital, *Etz Hayyim* |
| Classical Samkhya | 7 | 6 | Linear chain | Ishvarakrishna, *Samkhya Karika* |
| Taoist DDJ | 5 | 4 | Linear chain | *Daodejing* Ch. 42 |
| Ishraqi Illuminationist *(new)* | 7 | 6 | Linear chain | Suhrawardi, *Hikmat al-Ishraq* (Walbridge & Ziai 1999) |
| Genesis Creationist (control) | 8 | 2 | Branching tree | Genesis 1:1–2:3 |

---

## Encoding Protocol

All schemas follow the seven-rule DAG contract established in Ceisiwr (2026a):
- Single-root DAG, 4–20 nodes
- 5 edge types: `emanation`, `creation`, `fragmentation`, `contraction`, `reflection`
- 9 functional roles: `source`, `first_emanation`, `intellect`, `soul`, `intermediary`, `fallen`, `demiurge`, `matter`, `process`
- Granularity Rule: collective governance tiers encoded as single nodes
- Alternative encodings documented for all structurally contested decisions

See `notes/suhrawardi_scouting_report.md` for the Ishraqi encoding rationale and sensitivity analysis.

---

## Citation

If you use this code or data, please cite:

> Ceisiwr, Erydir, and Lumos Aureon. 'Structural Invariance Under Corpus Expansion: Proclus and Ishraqi Illuminationism Confirm Topology-Family Stability in Emanation Hierarchies'. Zenodo, 29 March 2026. https://doi.org/10.5281/zenodo.19305988

The predecessor study:

> Ceisiwr, E. (2026a). Convergent cosmological architecture: A computational graph-theoretic analysis of emanation hierarchies across nine sacred and philosophical traditions. *Digital Scholarship in the Humanities* [submitted]. GitHub: https://github.com/OwainGlyndwr1400/emanation-topology

---

## Licence

MIT — code and data are freely reusable with attribution.

---

*Awen Grid Programme — Independent Research*
*Academia.edu: https://independentresearcher.academia.edu/ErydirCeisiwr*
