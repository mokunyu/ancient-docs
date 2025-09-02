# AncientDoc: Benchmarking Vision-Language Models on Chinese Ancient Documents

<div align="center">

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](link_to_paper) 
[![Dataset](https://img.shields.io/badge/Dataset-HuggingFace-blue)](link_to_dataset) 
[![Model](https://img.shields.io/badge/Models-Baselines-green)](link_to_models)

</div>

## 📖 Introduction
Chinese ancient documents are invaluable carriers of history and culture, but their **visual complexity**, **linguistic variety**, and **lack of benchmarks** make them challenging for modern Vision-Language Models (VLMs).  
We introduce **AncientDoc**, the **first benchmark** designed for evaluating VLMs on **Chinese ancient documents**, covering the full pipeline from **OCR** to **knowledge reasoning**.

- **5 Tasks:** Page-level OCR, Vernacular Translation, Reasoning-based QA, Knowledge-based QA, Linguistic Variant QA  
- **14 Categories:** 100+ books, ~3,000 pages across dynasties from Warring States to Qing  
- **Rich Annotations:** OCR + semantic translation + multi-level QA pairs  
- **Comprehensive Evaluation:** CER, Precision/Recall/F1, CHRF++, BERTScore, and human-aligned GPT-4o scoring

<p align="center">
  <img src="teaser.png" width="700">
</p>

---

## 🏛 Dataset Overview

- **Source:** Digitized ancient documents from Harvard Library and others  
- **Dynasty Coverage:** From Warring States, Han, Tang, Song, Ming to Qing  
- **Category Coverage:** 14 semantic categories (e.g., collected works, Chuci-style poetry, medicine, astronomy, literary criticism, art)  
- **Total Size:** ~3,000 page images, with annotations across five tasks  

<p align="center">
  <img src="figures/dynasty_distribution.png" width="350">
  <img src="figures/category_distribution.png" width="350">
</p>

---

## 🧩 Task Definition

1. **Page-level OCR** – extract complete text in correct reading order (vertical right-to-left, with annotations).  
2. **Vernacular Translation** – translate classical Chinese into modern vernacular.  
3. **Reasoning-based QA** – infer implicit meanings, causality, and ideology.  
4. **Knowledge-based QA** – answer factual and cultural questions from texts.  
5. **Linguistic Variant QA** – recognize rhetorical devices, stylistic features, and literary styles.

<p align="center">
  <img src="figures/task_examples.png" width="700">
</p>

---

## 📊 Evaluation Metrics

- **OCR Task:** CER, Char Precision/Recall/F1  
- **Translation & QA Tasks:** CHRF++, BERTScore (BS-F1)  
- **LLM-as-a-Judge:** GPT-4o scoring aligned with human ratings

---

## 🚀 Baseline Results

We evaluate **open-source** (Qwen2.5-VL, InternVL, LLaVA, etc.) and **closed-source** (GPT-4o, Gemini2.5-Pro, Doubao-V2, etc.) VLMs.  

- **OCR:** Gemini2.5-Pro achieves lowest CER (32.03)  
- **Translation:** Gemini2.5-Pro leads with BS-F1 72.5  
- **Reasoning QA:** Qwen2.5-VL-72B shows strongest implicit reasoning  
- **Knowledge QA:** GPT-4o achieves best factual QA performance  
- **Variant QA:** GPT-4o & Gemini2.5-Pro excel in stylistic recognition

<p align="center">
  <img src="figures/results_table.png" width="750">
</p>

---

## ⚙️ Usage

### Dataset Download
```bash
git clone https://github.com/your_repo/AncientDoc
cd AncientDoc
# Download images and annotations
bash scripts/download_data.sh
```

### Data Format
Each JSONL file contains:
```json
{
  "image": "class/book/page_001.png",
  "task": "OCR",
  "question": "Please extract the text...",
  "answer": "夫天之所..."
}
```

### Evaluation
```bash
python evaluate.py   --model qwen2.5-vl-7b   --task OCR   --data data/OCR.jsonl   --metrics cer char_f1
```

---

## 📌 Citation
If you use AncientDoc in your research, please cite:
```bibtex
@article{ancientdoc2025,
  title={Benchmarking Vision-Language Models on Chinese Ancient Documents: From OCR to Knowledge Reasoning},
  author={Anonymous},
  journal={Under Review},
  year={2025}
}
```

---

## 🔗 Resources
- 📂 Dataset: [HuggingFace Link](link_to_dataset)  
- 📑 Paper: [arXiv Link](link_to_paper)  
- 🤖 Baseline Models: [Weights & Logs](link_to_models)  
