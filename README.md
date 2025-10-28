# Cyber Essentials — CheckLoop (Colab Notebooks)

**Repository:** SamwelMakombe-cloud/ce-colab-notebooks  
**Author:** Samwel Christopher Makombe

This repository contains the Colab notebooks for **CheckLoop**, an assessor-focused pipeline that combines rule logic, semantic information extraction, and rubric-guided LLMs to support consistent, explainable Cyber Essentials (CE) assessments.

---

## Notebooks

| Stage | Notebook file | Open in Colab | Purpose |
|---|---|---|---|
| 1 | `Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb) | Load and explore the development corpus; structure questions, answers, and notes for downstream modules. |
| 2 | `data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb) | Class balancing and augmentation for descriptive items while preserving label integrity. |
| 3 | `Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb) | Encode CE marking rules (CFG) and extract semantic frames/entities (spaCy + SRL) aligned to the marking guide. |
| 4 | `zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb) | Compare zero-shot vs fine-tuned **Mistral-7B** under CE-specific rubrics; safe rendering for GitHub. |
| 5 | `zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb) | Evaluate **LLaMA-3.1-8B** with CE-specific rubric prompts; report comparisons and metrics. |
| 6 | `INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb) | Run the full inference pipeline on held-out forms; save predictions and supporting explanations. |
| 7 | `streamlitdeployment_clean.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/streamlitdeployment_clean.ipynb) | Launch the Streamlit demo (assessor UI, overrides, exportable audit artefacts). |

> If a link 404s, confirm the filename in the repo matches exactly (including case and symbols).

---

## Project objectives

- **Consistency with defensible rationales.** Reduce assessor-to-assessor variability by combining deterministic checks, structured list validation, and rubric-guided LLM scoring. Every decision is accompanied by a concise reason (rule ID, recovered frame, or rubric-aligned rationale).
- **Human-in-the-loop control.** Surface explanations for each judgement and allow assessor overrides with audit logging, so automation accelerates review without removing expert judgement.
- **Dependable whole-form outcomes.** Apply conservative fusion and cross-question constraints (for example, missing A6.2.x versions escalate to MIR; firewall “No” cascades to dependent items) to avoid inconsistent states.
- **Pre-assessment and transparency.** Support applicant self-checks and provide a reference for scheme-level monitoring of assessor consistency.

---

## Methodology (summary)

- **Research design.** Pragmatist **Design Science Research**: deductively encode CE marking guidance; use exploratory data analysis on labelled forms; connect both via abductive reasoning to shape the hybrid architecture. Dataset split: development vs assessor-marked hold-out.
- **Module 1 — Rule engine (closed-form).** Machine-checkable items (IDs, yes/no, some MCQs) mapped to explicit rules with fixed precedence (**Fail > MIR > Non-Compliant > Compliant**). Outputs include the schema label and the minimal rule-ID reason.
- **Module 2 — Semantic frames (lists).** Normalise list answers into slot–value frames (provider, product, version, quantity, role/scope). Validate completeness (e.g., A6.2.x requires versions) and verify software against end-of-life catalogues.
- **Module 3 — Rubric-guided LLMs (descriptive).** Prompt **Mistral-7B** and **LLaMA-3.1-8B** with CE-specific rubrics to produce **Compliant/Non-Compliant** (and **More Information Required** only where permitted) with a short justification; optional LoRA adapters improve domain alignment.
- **Fusion & dependencies.** Reconcile module outputs with conservative tie-breaking and monotonic cross-question constraints; produce a clear per-form summary.
- **Assessor UI (Streamlit).** Upload a form, inspect per-item rationales, record overrides, and export audit artefacts (CSV/JSON/PDF).

*Pilot results on a small hold-out set show strong performance on the Compliant class (high precision/recall), with targeted improvements planned for minority classes (NC/MIR).*

---

## How to use

1. Open any notebook via the **Colab** badge above.  
2. If notebooks reference Google Drive data, run the first cell to mount Drive and adjust paths as needed.  
3. Follow the per-notebook instructions (install prerequisites, run cells in order).  
4. For the Streamlit demo, the notebook guides you through launching the app.

---

## Citation

Makombe, S.C. (2025). *Assessor-Focused Automation of Cyber Essentials Compliance via Rule Logic and Semantic LLMs*. MSc Data Science, Robert Gordon University.
