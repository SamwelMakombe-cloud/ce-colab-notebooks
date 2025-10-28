# Cyber Essentials – Colab Notebooks (CheckLoop)

Repository: **SamwelMakombe-cloud/ce-colab-notebooks**  
Author: **Samwel Christopher Makombe**

This repository contains Google Colab notebooks for the **CheckLoop** pipeline: a hybrid rule-logic + semantic-NLP + rubric-guided LLM system for Cyber Essentials assessments. Use the badges to open each notebook directly in Colab.

---

## 📘 Notebooks

| Stage | Notebook | Open in Colab | Summary |
|---|---|---|---|
| 1 | `Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Data_Preparation_and_Exploration_for_development_corpus_CLEAN_WITH_OUTPUTS.ipynb) | Loads and explores the development corpus; structures Q/A/notes for downstream processing. |
| 2 | `data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/data_augmentation_&_balance_for_descriptive_data_CLEAN_WITH_OUTPUTS.ipynb) | Class balancing and augmentation for descriptive answers; preserves label integrity. |
| 3 | `Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/Rules_SemanticFrames_Extraction_1_CLEAN_WITH_OUTPUTS.ipynb) | CFG rule encoding + semantic frame/entity patterns (spaCy + SRL) aligned to CE marking guide. |
| 4 | `zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zero_shot_VS_finetune_Mistral_7B_with_rubrics_FENCES_STRICT_SAFE_WITH_OUTPUTS.ipynb) | Zero-shot vs fine-tuned **Mistral-7B** with rubric-guided scoring; safe-rendering for GitHub. |
| 5 | `zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/zeroshot_fine_tuned_LLaMA_8B_with_rubrics_4_CLEAN_WITH_OUTPUTS.ipynb) | Fine-tuned **LLaMA-3.1-8B** with CE-specific rubric prompts; comparisons and metrics. |
| 6 | `INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/INFERENCE_ON_UNSEEN_DATA_CLEAN_WITH_OUTPUTS.ipynb) | Inference pipeline on held-out/unseen forms; saves predictions and explanations. |
| 7 | `streamlitdeployment_clean.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SamwelMakombe-cloud/ce-colab-notebooks/blob/main/streamlitdeployment_clean.ipynb) | Streamlit demo: assessor UI, overrides, and XAI artefacts for decision support. |

> ⚠️ If a filename in your repo differs slightly (e.g., the LLaMA notebook suffix), edit the link path to match exactly.

---

## 🧩 What’s inside (high level)

- **Rule engine (CFG + frames):** formalises CE marking logic and auto-fail checks.  
- **Semantic frames:** tools/devices/roles extraction via spaCy + SRL patterns.  
- **Rubric-guided LLMs:** Mistral-7B and LLaMA-3.1-8B evaluated for CE-specific rubrics.  
- **Evaluation & inference:** dev vs hold-out splits, MIR handling, whole-form logic.  
- **UI demo:** Streamlit interface with overrides and exportable audit artefacts.

---

## ▶️ How to run

1. Click a **Colab** badge above.  
2. If using Google Drive data, mount Drive in the first cell.  
3. Follow per-notebook instructions (install cells are included where needed).  

---

## 📚 Suggested citation

Makombe, S.C. (2025). *Assessor-Focused Automation of Cyber Essentials Compliance via Rule Logic and Semantic LLMs*. MSc Data Science, Robert Gordon University.

---

## 🛡️ License

MIT — see `LICENSE` if present. Otherwise, assume standard academic non-exclusive use.
