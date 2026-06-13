<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2F81F7,100:7F77DD&height=200&section=header&text=Sehyun%20Cho&fontSize=58&fontColor=ffffff&fontAlignY=36&desc=AI%2FML%20Engineer%20%C2%B7%20CS%20%40%20Konkuk%20University%20%C2%B7%20GPA%203.93%2F4.5&descSize=18&descColor=ffffff&descAlignY=56" width="100%" alt="header" />

<p>
  <a href="mailto:lysopa@naver.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>
  <a href="https://github.com/Ssopaa"><img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white"/></a>
</p>

</div>

---

## About Me

Computer Science Undergraduate · GPA **3.93 / 4.5**

- **Email** — lysopa@naver.com
- **GitHub** — [github.com/Ssopaa](https://github.com/Ssopaa)
- **Location** — Gwangjin-gu, Seoul, Republic of Korea

---

## Tech Stack

**ML / Deep Learning**

<img src="https://skillicons.dev/icons?i=python,pytorch,tensorflow,sklearn,opencv" />
<img src="https://img.shields.io/badge/OpenAI_CLIP-412991?style=flat-square&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/YOLOv8-00FFFF?style=flat-square&logo=yolo&logoColor=black"/>

**Backend / Web**

<img src="https://skillicons.dev/icons?i=fastapi,ts,react,nextjs,tailwind,mysql" />

**Tools**

<img src="https://skillicons.dev/icons?i=git,github,vscode,vercel" />
<img src="https://img.shields.io/badge/Roboflow-6706CE?style=flat-square&logo=roboflow&logoColor=white"/>

---

## Projects

<table width="100%">
<tr><td width="850">

### INPOSE — AI-Driven Matching & CRM System

`Capstone` · `Solo` · `In production`

An AI CRM built into the live social-matching service [**Inpose**](https://inpose.co/) — it automatically clusters feed images by visual semantics and learns each user's behavior to power personalized **job-posting and feed recommendations**.

**My role** — Designed and built the entire ML pipeline single-handedly: embedding extraction, clustering, inference server, user-affinity module, and production deployment.

- Extracted **CLIP ViT-L/14** embeddings from **384,761** images → PCA + **K-Means (K=500)**; chose K-Means over DBSCAN/HDBSCAN after analyzing failure modes on high-dimensional embeddings
- Real-time inference at **~13ms/image (~78.8 img/s, GPU)** via cosine-distance centroid matching
- Behavior-weighted user affinity module (view/like/comment/scrap), deployed with **FastAPI**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![CLIP](https://img.shields.io/badge/OpenAI_CLIP-412991?style=flat-square&logo=openai&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
&nbsp;
[![Service](https://img.shields.io/badge/Service-inpose.co-2F81F7?style=flat-square&logo=googlechrome&logoColor=white)](https://inpose.co/)

**[Details →](projects/inpose.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### Trash is YOLO — AI Bulky Waste Management System

`Grand Prize ×2` · `Solo (code & research)`

A service that recognizes bulky household waste from a camera in real time and automatically calculates the disposal fee per item. Won top prize at two competitions.

**My role** — Owned the full codebase end-to-end and led the research report — from data pipeline to model training, evaluation, and the service prototype.

- **YOLOv8n** (imgsz=800, 300 epochs) → **mAP@50 98.1% · mAP@50-95 93.2%**
- Built the full data pipeline on the NIA dataset: JSON→YOLO label conversion, polygon/box parsing, multi-class augmentation (albumentations)
- Designed an end-to-end service prototype with automated fee calculation

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-00FFFF?style=flat-square&logo=yolo&logoColor=black)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)

**[Details →](projects/trash-is-yolo.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### ARAKON — Defense Reconnaissance AI Model

`Team project` · `Konkuk Dream Semester`

A defense-reconnaissance AI that detects camouflaged/occluded military targets (personnel, vehicles, APCs). Team project under Konkuk University's Dream Semester program.

**My role** — Led data collection & annotation, and ran the architecture-search and hyperparameter-tuning experiments.

- Built the dataset: web scraping + synthetic **ARMA 3** scenarios, **1,800+** images labeled via Roboflow (3 classes)
- Architecture search: HybridTwoWay (CNN+ViT) → SAM → **YOLOv8 + CBAM**; tuned class/box/DFL loss & Cosine Annealing → **mAP@50 0.93** (+7%p APC vs. baseline)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-00FFFF?style=flat-square&logo=yolo&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)

**[Details →](projects/arakon.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### Roadkill Detection Assist System

`Team (AI role)` · `Agentic dev`

An AI-assisted traffic-control system that pre-screens road snapshots for animals/carcasses so operators only review images that need a human decision. Built through a controlled agentic-AI workflow.

**My role** — Owned the AI pipeline: YOLOv8 training on 67,275 images (3 classes), a data-existence verification gate, a two-stage confidence threshold (0.3 detect / 0.6 alert), and the inference→webhook alert pipeline.

- Validation **mAP@50 0.994**; honest external test (12 imgs) → precision 1.0, recall 0.67
- Rejected the LLM's single-threshold design for a two-stage detect/alert split tuned on held-out data

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-00FFFF?style=flat-square&logo=yolo&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)

**[Details →](projects/roadkill-detection.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### Digital Image Processing — Classical CV

`Solo` · `Classical CV (no DL)`

Two vision tasks solved with **classical image processing only** — a counterpoint showing I understand the fundamentals beneath modern detectors.

**My role** — Built both pipelines solo.

- **Eye Image Segmentation** — pupil-center detection via threshold → morphology → multi-radius circular template matching (IR/RGB/Depth)
- **Pathology Slide Classification** — normal vs cancer-suspected patches via hand-engineered features (tissue ratio, morphological irregularity, local density) + rule classifier

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)

**[Details →](projects/digital-image-processing.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### KU Welfare Web — Rental & Printing Portal

`Live Service` · `PM + Frontend` · `Team of 2`

The official portal of Konkuk University's Student Welfare Committee, digitalizing campus rental and printing operations. Currently live in production.

**My role** — Project planning (PM), frontend architecture & implementation, deployment, and ongoing maintenance/operations.

- Digitalized rental & printing workflows, drastically reducing administrative overhead

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
&nbsp;
[![Live](https://img.shields.io/badge/Live-ku--welfare--web.vercel.app-000000?style=flat-square&logo=vercel)](https://ku-welfare-web.vercel.app/)
[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/41-Welfare-Web/KU_WelfareWeb_FrontEnd)

**[Details →](projects/ku-welfare-web.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### CampusForm — Club Recruitment Platform

`Grand Prize` · `Frontend` · `Team`

An all-in-one recruitment web app that handles application collection, pass/fail management, bulk SMS, and interview scheduling in one place. Grand Prize at Kuit 6th Demoday.

**My role** — Frontend developer: built the Home / My / Manage / Notification pages and implemented & integrated the **smart scheduling** feature.

- **Smart interview scheduling** with automated time-slot recommendation and applicant self-adjustment

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
&nbsp;
[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/Konkuk-KUIT/CAMPUSFORM-Web)

**[Details →](projects/campusform.md)**

</td></tr>
</table>

---

## Research

> Research Intern @ **AI & Mobile Lab**, Konkuk University (Jan 2025 – Mar 2026) · Advisor: Prof. Seok-Ho Chang

<table width="100%">
<tr><td width="850">

### DL-Based Image Transmission & Frequency Allocation

`Published · KICS 2026`

DNN-based resource allocation for progressive image transmission over multi-frequency-band MIMO interference channels — jointly optimizing per-packet spectral efficiency, spatial multiplexing, sub-band combination, and transmit power via a PSNR-based, end-to-end differentiable loss.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)

**[Details →](projects/research-image-transmission.md)**

</td></tr>
</table>

<table width="100%">
<tr><td width="850">

### Task-Oriented Communication — Power & Frequency Allocation

`Industry-Academia Research`

DNN-based power allocation for D2D wireless networks (TensorFlow training pipeline, loss-function comparison study), plus graph-coloring / GNN frequency allocation benchmarked against an exhaustive-search baseline.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)

**[Details →](projects/research-resource-allocation.md)**

</td></tr>
</table>

---

## Publication

> Minjae Kim, **Sehyun Cho**, Seok-Ho Chang, *"Neural Network-Based Optimal Image Transmission Over Multiple-Frequency Band Interference Channels,"* **KICS Summer Conference 2026**, July 2026.
