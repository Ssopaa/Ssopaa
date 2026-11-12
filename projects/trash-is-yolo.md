# Trash is YOLO — AI Bulky Waste Management System

> 2025 · **Team of 4 — Team Lead** · 🏆 Grand Prize + Excellence Award
> Real-time bulky-waste detection with automated disposal-fee calculation.

## Overview

Disposing of bulky household waste in Korea requires manually identifying the item, looking up its fee, and buying a sticker — a slow, error-prone process. Trash is YOLO replaces it with a camera-based AI: point at the item, the model detects it in real time, and the service automatically computes the disposal fee.

Won the **Grand Prize** at the RISE AI-LivingLab Challenge 2025 and the **Excellence Award** (誠 category) at the 誠信義 AI Academic Competition 2025.

**Evidence:** [Training/data-processing source and competition materials](https://github.com/Ssopaa/Trash_Yolo) · [FastAPI inference prototype](https://github.com/Ssopaa/trashyolowa).

## Architecture

```mermaid
flowchart LR
    A[NIA dataset<br/>JSON labels] --> B[label conversion<br/>JSON → YOLO]
    B --> C[augmentation<br/>albumentations]
    C --> D[YOLOv8n training<br/>imgsz=800, 300 epochs]
    D --> E[detection model]
    E --> F[fee calculation<br/>per detected item]
```

## Pipeline details

- **Data** — built on the public NIA bulky-waste dataset; wrote a converter handling both `POLYGON` and `BOX` annotation formats into YOLO format.
- **Augmentation** — albumentations pipeline (horizontal flip, brightness/contrast, rotation ±15°, shift-scale-rotate) with keypoint-aware bounding-box transforms.
- **Training** — YOLOv8n at imgsz=800, 300 epochs, auto batch-size search, with separate experiments for top-only classes and a dedicated sofa classifier.
- **Service** — end-to-end prototype mapping each detected class to its disposal fee.

## Administrative workflow and feasibility

Rather than focusing solely on model accuracy, I researched **Gwangjin-gu's existing bulky-waste reporting process**, including manual classification, fee lookup, reporting, and paper receipt/sticker handling.

- **User flow** — prototyped photo capture, item recognition, fee calculation, and payment interaction, and designed a **staff management dashboard**.
- **Municipal integration proposal** — suggested replacing paper receipts with a **QR-based mobile receipt** linked to reporting and administrative processing.
- **Feasibility feedback** — contacted Gwangjin-gu district office and received positive feedback about the proposal.

**Deployment boundary:** the fee-recognition service was prototyped; the QR-based receipt and municipal integration were **proposed, not implemented in the district's live system**.

## Results

| Metric | Value |
|--------|-------|
| Model | YOLOv8n (imgsz=800) |
| Precision | **~98%** |
| mAP@50 | **98.1%** |
| mAP@50-95 | **93.2%** |
| Training | 300 epochs |

## My role

**Team lead** of a 4-person team. Owned the **full codebase end-to-end** — data pipeline, augmentation, training/validation, and the service prototype — and **led the research report** that the competition submissions were built on.

## Tech stack

`Python` · `YOLOv8 (Ultralytics)` · `albumentations` · `OpenCV` · `PyTorch`
