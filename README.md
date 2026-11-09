# Behavioral Anomaly Detection in Agentic Tool-Use Sequences

**Topic T1** · Data Science Lab, ELTE Faculty of Informatics
**Student:** Alyasar Jabbarli · **Supervisor:** Oumaima Araar

LLM agents act on the world through tool calls: e-mail, files, payments, code execution. When an agent is manipulated (prompt injection, memory or tool poisoning) or simply goes wrong, the first visible symptom is an unusual **sequence of tool calls**. This project learns what normal tool use looks like for different agent workflows and flags deviations that may indicate compromised or unsafe behavior, while keeping false alarms low.

## Project links
| Tool | Link |
|---|---|
| Written work (Overleaf) | _add link_ |
| Reference library (Zotero) | _add link_ |
| Task board (GitHub Projects) | _add link_ |

## Objectives
1. Define a representation for agent trajectories: tool names, order, and coarse argument features.
2. Establish behavioral baselines of normal tool use per workflow.
3. Detect deviations with one-class methods of increasing expressiveness:
   - n-gram / Markov models
   - Isolation Forest / one-class SVM on engineered features
   - deep sequence models (LSTM next-call prediction, autoencoders)
4. Evaluate across several workflows with:
   - precision, recall, F1
   - ROC-AUC
   - FPR at fixed recall
   - detection delay

## Repository structure
```
data/
  raw/           original trace files (not committed if large; see data/README)
  processed/     cleaned, tokenised trajectories
notebooks/       exploration and analysis (numbered: 01_..., 02_...)
src/
  detectors/     anomaly detection models
experiments/
  configs/       one YAML per experiment run
results/         metrics, figures (generated)
docs/
  paper-notes/   one markdown file per reviewed paper
reports/
  milestone1/    M1 report: PDF and LaTeX source (master copy lives in Overleaf)
```

## Milestones
- [x] **M1:** Field overview, threat and method taxonomy, scope
- [ ] **M2:** In-depth literature review; select trace sources
- [ ] **M3:** Data pipeline and statistical baselines
- [ ] **M4:** Deep sequence models and evaluation across workflows
- [ ] **Final:** Report and presentation

## Setup
```bash
python -m venv .venv
.venv\Scripts\activate        # Windows (PowerShell)
pip install -r requirements.txt
```

## Changelog
- _2026-10-21_: Milestone 1 report drafted.
- _2026-11-09_: Repository set up; M1 report updated with the key-paper list agreed with the supervisor.
