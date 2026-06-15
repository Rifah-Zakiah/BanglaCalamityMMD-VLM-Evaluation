# How Well Do Vision-Language Models Understand Bangla Disasters? A Comparative Evaluation

## Overview

This project evaluates the effectiveness of four state-of-the-art **Vision-Language Models (VLMs)**: **BLIP-2**, **Qwen2-VL-2B**, **LLaVA-1.5**, and **Gemma-3-4B**, for classifying natural disasters in Bangladesh using native Bangla text and images.

We utilized the **BanglaCalamityMMD** dataset and implemented three evaluation settings:
- **Zero-Shot Inference**
- **Few-Shot Learning** (k=4 with confidence-based semantic guardrail fall-back )
- **Hybrid Feature Adapter** (injects frozen multi-modal features along with sparse high-dimensional TF-IDF features into a supervised linear classifier)
---

## Overall Performance

### Table 1: Zero-Shot Test Performance

| Model         | Accuracy (%) | Macro Precision | Macro Recall (%) | Macro F1 (%) |
|---------------|--------------|-----------------|------------------|--------------|
| BLIP-2        | 84.68        | 88.90           | 84.83            | 85.03        |
| Qwen2-VL-2B   | 82.91        | 84.14           | 83.08            | 82.43        |
| LLaVA-1.5     | 84.43        | 88.62           | 84.58            | 84.74        |
| Gemma-3-4B    | 81.01        | 85.39           | 81.04            | 81.62        |

### Table 2: Few-Shot Test Performance

| Model         | Accuracy (%) | Macro Precision | Macro Recall (%) | Macro F1 (%) |
|---------------|--------------|-----------------|------------------|--------------|
| BLIP-2        | 87.85        | 88.14           | 87.99            | 87.77        |
| Qwen2-VL-2B   | 88.23        | 88.57           | 88.36            | 88.18        |
| LLaVA-1.5     | 88.10        | 88.43           | 88.24            | 88.04        |
| Gemma-3-4B    | 89.75        | 90.10           | 89.88            | 89.72        |

### Table 3: Feature Adapter Test Performance

| Model         | Accuracy (%) | Macro Precision | Macro Recall (%) | Macro F1 (%) |
|---------------|--------------|-----------------|------------------|--------------|
| BLIP-2        | 93.29        | 93.61           | 93.28            | 93.29        |
| Qwen2-VL-2B   | 93.92        | 94.10           | 93.93            | 93.93        |
| LLaVA-1.5     | 94.81        | 95.14           | 94.86            | 94.80        |
| Gemma-3-4B    | 92.53        | 92.67           | 92.61            | 92.40        |

### Best Results
- **Zero-Shot**: BLIP-2 → **84.68%** accuracy
- **Few-Shot**: Gemma-3-4B → **89.75%** accuracy
- **Feature Adapter**: LLaVA-1.5 → **94.81%** accuracy

---

## Dataset

- **Dataset Name**: BanglaCalamityMMD
- **Link**: [https://data.mendeley.com/datasets/7dggbjn5sd/1](https://data.mendeley.com/datasets/7dggbjn5sd/1)
- **Description**: A multimodal benchmark dataset for disaster identification in low-resource Bangla language containing images and Bangla captions across 8 disaster categories.

---
## Repository Contents
This repository contains all the **Google Colab notebooks** used in the project, separated in folders for the three approaches used:
#### zeroshot
- `ZeroShot_All_BanglaCalamityMMD.ipynb`
#### fewshot
- `BLIP2_Qwen2VL_Fewshot_BanglaCalamityMMD.ipynb`
- `LLaVA_Gemma3_Fewshot_BanglaCalamityMMD.ipynb`
#### feature adapter
- `BLIP2_QWEN2VL_Feature_Adapter_BanglaCalamityMMD.ipynb`
- `Gemma3_LLaVA_Feature_Adapter_BanglaCalamityMMD.ipynb`

Additional files include detailed classification reports and confusion matrices.

---

## Reproduction Instructions

All experiments were conducted on **Google Colab**.

### Steps to Reproduce:

1. Clone this repository or simply download the specific notebooks mentioned.
2. Download the **BanglaCalamityMMD** dataset from [here](https://data.mendeley.com/datasets/7dggbjn5sd/1).
3. Upload the dataset to your Google Drive.
4. Open the notebooks in Google Colab and mount your Google Drive.
5. Update the dataset path in the notebooks accordingly and run the cells.

_Note: Due to VRAM limitations on free Colab instances, some models may require cloud APIs or high-RAM runtime. The results may vary as well._

---

## Authors
- Rifah Zakiah (ID-2252421024)
- Latifa Nishat Nishi (ID-2252421062)
- Safwat Bushra Afreen (ID-2252421068)
- Maishan Nadis (ID-2252421118)

**Course:** Artificial Intelligence Laboratory (CSE-4202)

**Supervisor:** Lecturer Sayma Ahmed Suha & Lecturer Md. Mahabubur Rahman

**Department of CSE, BUP**
