# 🧠 osipi-gsoc2026-asl-qc

<div align="center">

![OSIPI](https://img.shields.io/badge/Organization-OSIPI-007A8A?style=for-the-badge)
![GSoC](https://img.shields.io/badge/Program-Google%20Summer%20of%20Code%202026-4285F4?style=for-the-badge&logo=google)
![Python](https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python)
![Status](https://img.shields.io/badge/Status-Pre--Application%20Prototype-yellow?style=for-the-badge)

**Quality Check Toolbox V1.0 — Exploratory Prototype**

*GSoC 2026 Pre-Application Work — Automated QC for ASL MRI Data*

[View Notebook](#-notebook) · [QC Modules](#-qc-modules) · [Run It](#-running-the-code) · [Contact](#-contact)

</div>

---

## 👤 Applicant

| Field | Details |
|-------|---------|
| **Name** | Ovie Great Ohwoka |
| **University** | Obafemi Awolowo University, Ile-Ife, Nigeria |
| **Programme** | B.Sc. Physics / Engineering Physics (2026) |
| **Email** | greatohwoka@student.oauife.edu.ng |
| **GitHub** | [bugindacodeQ](https://github.com/bugindacodeQ) |
| **LinkedIn** | [ovie-ohwoka-951429371](https://linkedin.com/in/ovie-ohwoka-951429371) |
| **Project** | Quality Check Toolbox V1.0 for ASL MRI Data |
| **Mentors** | Maria Mora, Sudipto Dolui |

---

## 🔬 What This Repository Is

This is a **pre-application prototype** built before GSoC 2026 begins, to demonstrate hands-on understanding of the QC metrics I plan to implement in the [OSIPI Quality Check Toolbox V1.0](https://osipi.ismrm.org/) project.

Arterial Spin Labeling (ASL) MRI measures cerebral blood flow non-invasively — but its sensitivity to acquisition artefacts makes quality control a persistent bottleneck in large clinical studies. Scans that pass visual inspection can still contain corrupted CBF maps due to motion, poor M0 calibration, or scanner instability. This toolbox automates that detection.

---

## ✅ QC Modules

| # | Module | What It Checks |
|---|--------|----------------|
| 1 | **SNR** | Signal-to-noise ratio per volume and per slice |
| 2 | **M0 Calibration** | Saturation and signal dropout in calibration image |
| 3 | **Control-Label Pattern** | Alternating acquisition pattern integrity |
| 4 | **Motion Tracking** | Framewise displacement — flags volumes with excessive movement |
| 5 | **CBF Histogram** | Physiological plausibility of cerebral blood flow values |
| 6 | **Spatial CoV & RMS** | Signal uniformity and inter-volume instability |
| 7 | **Tissue Mask Quality** | GM/WM/CSF CBF distributions vs expected ranges |
| 8 | **QEI Composite Score** | Weighted aggregate of all modules into one quality index |

---

## 📓 Notebook

**`OSIPI_QC_Prototype.ipynb`**

A complete end-to-end QC pipeline using synthetic ASL MRI data with:
- Rician noise (standard MRI noise model)
- Motion artefacts injected at known volumes
- Signal dropout in one corrupted volume
- M0 saturation in one slice
- Physiologically realistic CBF distributions per tissue class

Every module catches something, flags it, and contributes to the final QEI score.

---

## 🚀 Running the Code

### Google Colab (Recommended)

1. Open [colab.research.google.com](https://colab.research.google.com)
2. `File → Upload notebook` → select `OSIPI_QC_Prototype.ipynb`
3. `Runtime → Run all`

### Local

```bash
git clone https://github.com/bugindacodeQ/osipi-gsoc2026-asl-qc.git
cd osipi-gsoc2026-asl-qc
pip install numpy scipy matplotlib
jupyter notebook OSIPI_QC_Prototype.ipynb
```

### Dependencies

| Package | Purpose |
|---------|---------|
| `numpy` | Numerical operations & synthetic data |
| `scipy` | Statistical analysis |
| `matplotlib` | All plots and QEI gauge |

---

## 🗂️ Repository Structure

```
osipi-gsoc2026-asl-qc/
│
├── 📓 OSIPI_QC_Prototype.ipynb   ← Full QC pipeline notebook
├── 📄 README.md                  ← This file
└── proposal/
    └── GSoC2026_OSIPI_Proposal_OvieGreatOhwoka.pdf
```

---

## 🔭 From Prototype → Full GSoC Project

This prototype uses synthetic data. The full GSoC project extends it with:

- **Real data** — NIfTI/BIDS loading via `nibabel`, validated on the AURA ASL dataset
- **Data-driven thresholds** — calibrated across different scanner types and populations
- **Automated reports** — PDF/HTML quality reports per scan
- **CI/CD** — full `pytest` test suite with GitHub Actions
- **OSIPY integration** — module interface compatible with the unified OSIPY package

---

## 📚 References

- Alsop et al. (2015) — *Recommended implementation of ASL perfusion MRI* (White Paper)
- Mutsaerts et al. (2020) — *ExploreASL: QC framework for ASL MRI*
- Dolui et al. (2024) — *Quality Evaluation Index for ASL MRI*
- OSIPI GitHub: [github.com/OSIPI](https://github.com/OSIPI)

---

## 📬 Contact

**Ovie Great Ohwoka**
Physics / Engineering Physics — Obafemi Awolowo University, Nigeria
📧 greatohwoka@student.oauife.edu.ng
🔗 [linkedin.com/in/ovie-ohwoka-951429371](https://linkedin.com/in/ovie-ohwoka-951429371)

> *For OSIPI project queries, contact mentors at the OSIPI mailing list*

---

<div align="center">

![OSIPI](https://img.shields.io/badge/OSIPI-GSoC%202026-007A8A?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

*Built with curiosity and a deep respect for reproducible science.*

</div>
