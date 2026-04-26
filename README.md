# ShadowTeacher Distill

> CUDA/vLLM teacher to Snapdragon student distillation pipeline

## 1. Project Overview

**ShadowTeacher Distill** is a GitHub-ready project idea focused on **teacher-student learning, multimodal distillation, mobile deployment, efficient inference**.

Large VLMs and LLMs are powerful but not practical for always-on offline mobile inference. This project uses a larger desktop teacher to generate labels, masks, rationales, and hard examples, then distills them into small quantized students that run locally on a phone.

**Target area:** Snapdragon / Android edge AI  
**Primary users:** edge AI researchers, multimodal ML engineers, efficient AI practitioners

This repository is designed as a portfolio-grade edge AI project. The final target is **fully offline inference on a Snapdragon-powered Android device (for example, Galaxy S24 Ultra)**. When a larger model is mentioned, it is meant for the **desktop training/distillation/benchmark side**, while the shipped mobile app remains privacy-preserving and offline-first.

---

## 2. Why This Project Matters

This project shows the ability to think across:

- model design
- optimization and quantization or systems tuning
- runtime constraints
- reproducible benchmarking
- product-style engineering and evaluation



---

## 3. Core Features

- Desktop teacher pipeline for pseudo-labels, rationales, and hard-example mining
- Student models for detection, segmentation, and compact reasoning
- Quantization-ready student training and export path
- Distillation experiments for accuracy vs footprint tradeoff
- End-to-end evaluation from workstation training to mobile inference

---

## 4. Proposed System Architecture

1. Teacher model runs on CUDA workstation or server
2. Pseudo-label generator creates masks, object tags, and natural-language supervision
3. Student models are trained with distilled targets
4. Quantized students are exported for Snapdragon deployment
5. Android demo validates final offline behavior

---

## 5. Recommended Tech Stack

- CUDA workstation for teacher inference
- vLLM or other efficient serving stack for teacher orchestration
- PyTorch training for student models
- ONNX / LiteRT / mobile runtimes for deployment
- Experiment tracker for distillation variants


---

## 6. Data / Workload Ideas

COCO, LVIS subsets, referring-expression data, and custom mobile scenes collected for final deployment testing.

For a strong repository, keep one **small reproducible benchmark set** in the repo and document how the larger benchmark was prepared. That makes the project easier for others to run and review.

---

## 7. Milestone Plan

### Phase 1
Define teacher outputs and distillation targets

### Phase 2
Build pseudo-label generation pipeline

### Phase 3
Train lightweight students for detection/segmentation

### Phase 4
Quantize, export, and deploy students to Android

### Phase 5
Compare teacher quality vs student efficiency tradeoffs

### Final Deliverable
A working demo, a benchmark report, and clear ablations showing what changed performance or accuracy.

---

## 8. Evaluation Metrics

- Teacher-student accuracy gap
- Student FPS and latency on mobile
- Model size and RAM footprint
- Distillation gain over non-distilled baseline
- User-perceived reasoning quality


---

## 9. Suggested Repository Structure

```text
shadowteacher-distill/
├── README.md
├── app/ or src/
├── models/
├── scripts/
├── configs/
├── notebooks/ or reports/
├── benchmarks/
├── assets/
└── docs/
```


---
