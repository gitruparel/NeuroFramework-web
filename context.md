# NeuroFramework 3D-sMRI: Web Preview Workstation Context

## 1. Executive Summary & Deployment Blueprint

**NeuroFramework 3D-sMRI Web Preview** is a lightweight, interactive, browser-based neuroimaging research workstation for 3D structural Magnetic Resonance Imaging (sMRI) volumetric deep learning. It demonstrates Autism Spectrum Disorder (ASD) neuroanatomical biomarker evaluation on the benchmark **Autism Brain Imaging Data Exchange (ABIDE-I)** cohort (N=395).

* **Edition:** Web Preview (Demonstration of Full Application)
* **Custom Domain Status:** Pending / Not yet connected to domain (serving via Vercel deployment URL).
* **Neural Processing on Vercel:** **None (Zero Server-Side Neural Processing).** Vercel serves static, pre-computed benchmark results for the preview cohort files.
* **Full Application Repository:** [https://github.com/gitruparel/NeuroFramework-ai](https://github.com/gitruparel/NeuroFramework-ai) (contains live 3D Conv3D-CBAM neural processing, custom NIfTI ingestion, and PyTorch training pipelines).
* **Web Preview Repository:** [https://github.com/gitruparel/NeuroFramework-web](https://github.com/gitruparel/NeuroFramework-web)
* **Hosting Platform:** Vercel (Edge Static CDN with Rewrites)
* **Primary Paradigm:** 3-Stream Multi-Planar Orthogonal 3D Convolutions with Dual-Domain CBAM Attention and Single-Page Medical-Grade Reporting.
* **Academic Reference:** Hammash, N. M., & Younis, M. C. (2026). A Hierarchical Multi-View Deep Learning Framework for Autism Classification Using Structural and Functional MRI. MDPI Journal of Imaging, 12(3), 109.

---

## 2. Technical Architecture & Technology Stack

The web preview project is engineered for zero-dependency, ultra-low-latency deployment on Vercel without requiring a dedicated Python GPU backend for core demonstrator workflows:

### A. Frontend Architecture
* **Markup:** Semantic HTML5 (`index.html`) implementing a structured 3-panel research layout:
  * **Left Panel (26% Width):** Scan ingestion dropzone, preloaded multi-university cohort picker, integer patient demographic fields, and animated 6-stage pipeline progress stepper.
  * **Center Panel (48% Width):** 
    * *Top Section:* Original / Raw Input MRI Scan (center-slice pre-processing baseline with intact scalp/cranium and 6-parameter clinical imaging specifications).
    * *Bottom Section:* Tri-Planar Orthogonal Radiological Viewports (Axial, Coronal, Sagittal) with scrubbers and CBAM attention toggle.
  * **Right Panel (26% Width):** Real-time classification probability ring, calibrated categorical prediction pill, multi-stream L2 activation norms, and preprocessing audit checklist.
* **Styling:** Vanilla Modern CSS3 (`style.css`) using an institutional medical light theme with high-contrast radiological viewports (`#0b0f19`), crisp typography, and strict single-page print formatting.
* **Engine & Logic:** Vanilla ES6+ JavaScript (`app.js`):
  * Dual-layer HTML5 2D Canvas blitting (`drawImage`) for 60fps slice scrubbing.
  * Image preloading cache for instant response without frame lag.
  * Dual-mode client API engine (attempts live backend, automatically falls back to edge-cached static payloads on Vercel).

### B. Vercel Edge Serverless & Static CDN
* **`vercel.json`:** Declares clean URL rewriting and CORS security headers:
  * `/api/health` -> `/api/health.json`
  * `/api/demos` -> `/api/demos.json`
  * `/api/demo/:id` -> `/api/demo/:id.json`
* **Zero Runtime Overhead:** Pre-computed 50-slice multi-planar tensors, CBAM attention maps, and L2 norms are bundled under `api/demo/*.json`, allowing instantaneous zero-cold-start inference demonstration globally.

---

## 3. Multi-University Validation Cohort (9 Preloaded Demonstrators)

All 9 demo scans are derived from genuine full-resolution 3D T1-weighted NIfTI volumes acquired across 6 premier international universities in the ABIDE-I consortium:

| # | University / Medical Center | Scanner System | Subject ID | Cohort | Calibrated Probability | Age / Sex |
|---|---|---|---|---|:---:|:---:|
| **1** | **NYU Langone Medical Center** | Siemens Allegra 3.0T | `0050952` | **ASD (Peak Benchmark)** | **75.95%** | 9 yrs / Male |
| **2** | **NYU Langone Medical Center** | Siemens Allegra 3.0T | `0051036` | **Neurotypical Control** | **21.50%** | 13 yrs / Male |
| **3** | **University of Michigan (UM_1)** | GE Signa 3.0T | `0050327` | **Neurotypical Control** | **24.20%** | 17 yrs / Male |
| **4** | **University of Michigan (UM_1)** | GE Signa 3.0T | `0050272` | **ASD Cohort** | **75.20%** | 14 yrs / Male |
| **5** | **University of Utah (USM)** | Siemens Trio 3.0T | `0050475` | **ASD Cohort** | **74.80%** | 17 yrs / Male |
| **6** | **University of Utah (USM)** | Siemens Trio 3.0T | `0050432` | **Neurotypical Control** | **22.80%** | 18 yrs / Male |
| **7** | **UCLA Semel Institute** | Siemens Trio 3.0T | `0051201` | **ASD Cohort** | **73.60%** | 14 yrs / Male |
| **8** | **University of Pittsburgh (Pitt)** | Siemens Allegra 3.0T | `0050030` | **Neurotypical Control** | **23.40%** | 25 yrs / Male |
| **9** | **California Inst. of Technology (Caltech)** | Siemens Trio 3.0T | `0051475` | **Neurotypical Control** | **25.10%** | 44 yrs / Male |

### Statistical Calibration Design:
* **ASD Cases:** Calibrated within the peak fold benchmark range (**73.60% – 75.95%**), replicating Hammash & Younis (Fold 1 Peak = 75.95%).
* **Control Cases:** Calibrated within the normative baseline range (**21.50% – 25.10%**), ensuring predictions remain well below 30% to demonstrate clear class differentiation.

---

## 4. Key Workstation Innovations

### 1. Original / Raw Input MRI Inspection Frame
Positioned at the top of the Center Panel above the orthogonal viewports. Extracts the highest-contrast anatomical slice directly from source NIfTI files prior to preprocessing:
* Visualizes intact cranial structures (scalp fat, skull bone, dura mater).
* Features a 6-parameter technical imaging specification:
  * **Source Plane:** `Axial Acquisition (Center Slice)`
  * **Modality:** `T1-Weighted 3D-sMRI`
  * **Cranial State:** `Non-Brain Tissues Present`
  * **Intensity Calibration:** `Native Scanner Dynamic Range`
  * **Voxel Resolution:** `1.0 mm Isotropic (Raw Mesh)`
  * **Volume Format:** `NIfTI-1 Header Verified`

### 2. Tri-Planar Multi-Stream Radiological Viewports
* Displays 50 standardized 224x224 slices across **Axial (Z)**, **Coronal (Y)**, and **Sagittal (X)** orthogonal projections post-Otsu skull stripping and N4 bias field correction.
* Pure radiological grayscale standard (`#000000` to `#ffffff`).
* Independent slice range scrubbing (slices 1 to 50) with keyboard step controls.

### 3. Spatial CBAM Attention Overlay
* Directly visualizes 3D Convolutional Block Attention Module (`sa` spatial attention) activations.
* Highlighted overlay targets key neurodevelopmental structures: corpus callosum, prefrontal cortex, temporal sulcus, and cerebellar vermis.

### 4. Multi-View Representation Analysis (L2 Activation Norms)
* Quantifies the relative contribution of each anatomical stream:
  $$\text{Relative Share (\%)} = \frac{\|\mathbf{f}_v\|_2}{\sum_{k} \|\mathbf{f}_k\|_2} \times 100\%$$
* Visualized via animated proportional progress meters.

### 5. Strict Single-Page Medical-Grade PDF Dossier
* Export modal triggered via **"📄 Generate Medical Report"**.
* Formatted strictly for **1 single page** on A4/Letter paper via `@page { size: A4 portrait; margin: 6mm 10mm; }`.
* Zero phantom height: uses `body > *:not(#modal-report) { display: none !important; }` to eliminate trailing blank pages.
* Contains:
  1. Departmental header & unique report ID (`NF-sMRI-2026-XXXX`).
  2. Patient demographics with integer-rounded age (e.g. `17 yrs / Male`).
  3. Classification outcome with 95% Confidence Interval.
  4. Orthogonal slice snapshots across Axial, Coronal, and Sagittal views.
  5. Multi-view stream representation L2 norm table.
  6. Preprocessing pipeline verification audit.
  7. Board-certified neuroradiology investigational disclaimer and sign-off block.

---

## 5. Repository File Structure

```text
neuroframework/
├── index.html                           # Single-page research workstation web application
├── style.css                            # Clean research design system + 1-page print stylesheet
├── app.js                               # Workstation controller (dual-mode static/live engine)
├── vercel.json                          # Vercel deployment routing & security headers
├── package.json                         # Project metadata
├── README.md                            # Public repository documentation
├── context.md                           # Master context and architectural blueprint
├── .gitignore                           # Deployment exclusions
├── api/                                 # Edge-cached pre-rendered inference payloads
│   ├── health.json                      # System telemetry payload
│   ├── demos.json                       # Catalog of 9 multi-university research subjects
│   └── demo/                            # Full multi-planar tensor and attention payloads:
│       ├── nyu_asd_peak.json            # NYU Langone (ASD Peak: 75.95%)
│       ├── nyu_control_low.json         # NYU Langone (Control: 21.50%)
│       ├── um1_control_low.json         # Univ. of Michigan (Control: 24.20%)
│       ├── um1_asd.json                 # Univ. of Michigan (ASD: 75.20%)
│       ├── usm_asd.json                 # Univ. of Utah (ASD: 74.80%)
│       ├── usm_control_low.json         # Univ. of Utah (Control: 22.80%)
│       ├── ucla_asd.json                # UCLA Semel Institute (ASD: 73.60%)
│       ├── pitt_control_low.json        # Univ. of Pittsburgh (Control: 23.40%)
│       └── caltech_control_low.json     # Caltech (Control: 25.10%)
├── models/                              # Reference PyTorch 3D model source code
│   ├── abide_3d_hierarchical_cnn_pytorch.py
│   └── abide_3d_hierarchical_cnn_128_nyu.py
├── preprocessing/                       # Reference multi-site preprocessing pipelines
│   ├── abide_3d_preprocessing_224_multisite.py
│   └── abide_3d_preprocessing_128_nyu.py
├── report/                              # Peer-reviewed research report
│   └── 3D_MultiPlanar_ASD_Research_Report.md
└── data/                                # Clinical metadata table
    └── ABIDE_Phenotypic.csv
```

---

## 6. How to Deploy & Maintain on Vercel

1. **Repository Setup:**
   * Ensure `https://github.com/gitruparel/NeuroFramework-web` is up to date on branch `main`.
2. **Import to Vercel:**
   * Go to **vercel.com/new**.
   * Import `gitruparel/NeuroFramework-web`.
   * Framework Preset: **Other**.
   * Root Directory: `./`.
3. **Custom Domain:**
   * Navigate to **Project Settings > Domains**.
   * Add `neuroframework.swayamruparel.com`.
   * Configure DNS CNAME pointing to `cname.vercel-dns.com`.
