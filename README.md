# 🧠 NeuroFramework 3D-sMRI: Research Workstation

**Live Preview:** [neuroframework.swayamruparel.com](https://neuroframework.swayamruparel.com)

A high-performance 3D Structural Magnetic Resonance Imaging (sMRI) volumetric research workstation designed for multi-planar deep learning evaluation of Autism Spectrum Disorder (ASD).

Replicating and adapting the peer-reviewed methodology of **Hammash & Younis (MDPI 2026)**, this platform integrates:
- **3-Stream Hierarchical Conv3D Neural Network** with dual Channel-Spatial 3D CBAM attention and adaptive focal loss.
- **50-Slice Multi-Planar Orthogonal Viewports:** Interactive Axial, Coronal, and Sagittal scrubbing at 60fps.
- **Real Anatomical MRI Previews:** Unstripped pre-processing baseline inspection directly from raw T1-weighted scans.
- **Multi-University Validation Cohort:** Representative subjects across **NYU Langone**, **University of Michigan (UM_1)**, **University of Utah (USM)**, **UCLA**, **University of Pittsburgh (Pitt)**, and **Caltech**.
- **Medical-Grade Clinical AI Dossier:** Strict 1-page printable PDF report with quantitative L2 activation norms and QC audit verification.

---

## 🚀 Deployment on Vercel

This repository is optimized for one-click static hosting on **Vercel** (
euroframework.swayamruparel.com):
- Clean rewrites configured in ercel.json
- Pre-cached multi-planar tensors and attention maps in pi/
- Zero external runtime dependencies required for static CDN delivery

## 📄 Academic Reference
* **Hammash, N. M., & Younis, M. C. (2026).** *A Hierarchical Multi-View Deep Learning Framework for Autism Classification Using Structural and Functional MRI.* MDPI Journal of Imaging, 12(3), 109. [DOI: 10.3390/jimaging12030109]
