# 🧠 NeuroFramework 3D-sMRI: Web Preview Workstation

> **Notice:** This repository is the **Web Preview** of the full NeuroFramework application.  
> It is hosted on Vercel without server-side neural processing, serving verified pre-computed benchmark results for the preview cohort.  
> **To use the full application with live PyTorch neural processing, custom scan ingestion, and model training pipelines, refer to the [NeuroFramework-ai](https://github.com/gitruparel/NeuroFramework-ai) repository.**

---

## 🔬 Overview

NeuroFramework 3D-sMRI Web Preview is an interactive, browser-based neuroimaging research interface demonstrating multi-planar volumetric deep learning evaluation of Autism Spectrum Disorder (ASD).

Replicating and adapting the peer-reviewed methodology of **Hammash & Younis (MDPI 2026)**, this web preview provides:
- **Zero-Cold-Start Vercel CDN Delivery:** Instantaneous demonstration without heavy GPU backend infrastructure.
- **50-Slice Multi-Planar Orthogonal Viewports:** Interactive Axial, Coronal, and Sagittal scrubbing at 60fps.
- **Dual-Domain CBAM Attention Visualization:** Real-time spatial attention map overlays.
- **Real Anatomical MRI Previews:** Unstripped pre-processing baseline inspection directly from raw T1-weighted scans.
- **Multi-University Validation Cohort:** 9 representative subjects across NYU Langone, Univ. of Michigan (UM_1), Univ. of Utah (USM), UCLA, Univ. of Pittsburgh (Pitt), and Caltech.
- **Medical-Grade Clinical AI Dossier:** Single-page printable PDF report with quantitative L2 activation norms and QC audit verification.

---

## ⚡ Web Preview vs. Full Application

| Capability | Web Preview (`NeuroFramework-web`) | Full Application (`NeuroFramework-ai`) |
|---|:---:|:---:|
| **Hosting & Execution** | Vercel Edge CDN (Static) | Local / GPU Cluster (PyTorch) |
| **Neural Processing on Vercel** | ❌ None (Disabled) | N/A |
| **Cohort Results** | Pre-computed & Hardcoded | Live Model Inference |
| **Custom Scan Processing** | Preview Guidance Only | Full End-to-End Execution |
| **Otsu Skull Stripping & N4 Bias** | Pre-rendered | Automated Python Pipeline |
| **Model Training & Loss Functions** | N/A | Full Conv3D + CBAM + Focal Loss |
| **Repository Link** | Current Repository | [gitruparel/NeuroFramework-ai](https://github.com/gitruparel/NeuroFramework-ai) |

---

## 🌐 Deployment Status & Domain

* **Platform:** Vercel
* **Custom Domain Status:** *Pending / Not yet connected to domain* (accessible via default Vercel deployment URL).
* **Architecture:** Static Edge JSON API endpoints (`/api/health`, `/api/demos`, `/api/demo/:id`) with Vercel rewrites.

---

## 📄 Academic Reference
* **Hammash, N. M., & Younis, M. C. (2026).** *A Hierarchical Multi-View Deep Learning Framework for Autism Classification Using Structural and Functional MRI.* MDPI Journal of Imaging, 12(3), 109. [DOI: 10.3390/jimaging12030109]
