# Cyber Essentials — CheckLoop (Colab Notebooks)

**Repository:** [SamwelMakombe-cloud/ce-colab-notebooks](https://github.com/SamwelMakombe-cloud/ce-colab-notebooks)  
**Author:** Samwel Christopher Makombe

This repository contains Google Colab notebooks for **CheckLoop**, an assessor-focused automation pipeline that integrates rule-based logic, semantic information extraction, and rubric-guided large language models (LLMs) to support consistent and explainable Cyber Essentials (CE) assessments.

---

##  Notebooks

| Stage | Notebook file | Open in Colab | Purpose |
|:--:|:--|:--|:--|
| 1 | `Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb) | Loads and explores the development corpus, structuring questions, answers, and notes for downstream modules. |
| 2 | `data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb) | Performs class balancing and data augmentation for descriptive answers while preserving label integrity. |
| 3 | `Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb) | Encodes CE marking rules (CFG) and extracts semantic frames and entities (spaCy + SRL) aligned to the marking guide. |
| 4 | `zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb) | Compares zero-shot and fine-tuned **Mistral-7B** models under CE-specific rubrics (safe rendering for GitHub). |
| 5 | `zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb) | Evaluates **LLaMA-3.1-8B** using CE-specific rubric prompts and reports comparative performance metrics. |
| 6 | `INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb) | Runs the full inference pipeline on held-out forms and saves predictions with explanatory outputs. |
| 7 | `streamlitdeployment_clean.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/streamlitdeployment_clean.ipynb) | Launches the Streamlit assessor interface with override logging and exportable audit artefacts. |

> If a link returns a 404 error, confirm that the notebook name and capitalization in the repository match exactly.

---

##  Project Objectives

- **Consistency with defensible rationales** — Reduce assessor-to-assessor variability by combining deterministic rule checks, structured list validation, and rubric-guided LLM scoring. Each judgement includes an explicit rationale (rule ID, recovered frame, or rubric-aligned explanation).  
- **Human-in-the-loop control** — Present transparent reasoning for every automated judgement and allow assessors to override outputs with full audit logging, ensuring automation assists rather than replaces expert review.  
- **Dependable whole-form outcomes** — Apply conservative fusion and cross-question logic (e.g., missing A6.2.x versions → MIR; firewall “No” → downgrades dependent items) to avoid contradictory results.  
- **Pre-assessment and transparency** — Support applicant self-checks and enable scheme-level monitoring of assessor consistency.

---

##  Data & Privacy

This repository **does not** include any real Cyber Essentials applications or confidential material.  
It contains **only source code and demonstration notebooks**.

---

##  Methodology (Summary)

- **Research design** — A **Design Science Research** approach: CE marking guidance encoded deductively; labelled forms analysed inductively via exploratory data analysis; both reconciled through abductive reasoning. The dataset comprises 70 applications (65 development, 5 hold-out).  
- **Module 1 — Rule engine (closed-form)** — Encodes machine-checkable items (IDs, Yes/No, MCQs) into explicit rules with fixed precedence (**Fail > MIR > Non-Compliant > Compliant**). Outputs include both schema label and rule-ID justification.  
- **Module 2 — Semantic frames (lists)** — Normalises list answers into slot–value frames (provider, product, version, quantity, role/scope). Validates completeness (e.g., A6.2.x requires version info) and checks software against an end-of-life (EOL) catalogue.  
- **Module 3 — Rubric-guided LLMs (descriptive)** — Uses **Mistral-7B** and **LLaMA-3.1-8B** prompted with CE-specific rubrics to predict **Compliant / Non-Compliant / MIR**, providing concise rationales. Lightweight **LoRA** adapters enhance domain alignment.  
- **Fusion & dependencies** — Integrates module outputs using conservative tie-breaking and monotonic cross-question constraints, generating consistent whole-form results.  
- **Assessor UI (Streamlit)** — Interactive interface for uploading forms, reviewing per-item rationales, applying overrides, and exporting audit artefacts (CSV/JSON/PDF).

*Pilot evaluation on a held-out set achieved ~0.90 overall accuracy, with the “Compliant” class reaching precision 0.965 / recall 0.932 (F1 = 0.948). Continued work targets minority classes (NC/MIR) via data expansion.*

---

##  How to Use

1. Open any notebook via its **Open in Colab** badge above.  
2. If required, mount Google Drive in the first cell and adjust data paths.  
3. Execute cells sequentially following each notebook’s embedded instructions.  
4. For the Streamlit demo, run the final notebook to launch the local web app.

---

##  Authors & Contributors

- **Samwel Christopher Makombe** — Lead developer & maintainer  
- **Dr Hatem Ahriz** — Conceptualisation, supervision, and methodology guidance  
- **Victor Obahor** — Domain expertise, data access, and validation support

---

##  Citation

If you reference or adapt this work, please cite:

> **Makombe, S.C., Ahriz, H., & Obahor, V. (2025).**  
> *Cyber Essentials — CheckLoop (Colab Notebooks).*  
> GitHub repository. Commit 533d304.  
> [https://github.com/SamwelMakombe-cloud/ce-colab-notebooks](https://github.com/SamwelMakombe-cloud/ce-colab-notebooks)
