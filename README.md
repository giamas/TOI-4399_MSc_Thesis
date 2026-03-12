# Digging in the Stellar Noise: photometric and Doppler analysis of the young transiting system TOI-4399

This repository contains the data analysis pipeline, custom Python code, and simulation results for the Master's Thesis in Physics by **Giampaolo Maschietti** (University of Turin, 2024/2025).

The project focuses on the characterization of the young (~120 Myr) transiting system **TOI-4399**, a challenging target due to its extreme stellar activity and rapid rotation ($v \sin i \approx 24$ km/s).

## 🔭 Project Overview

Characterizing exoplanets around young, active stars requires advanced statistical techniques to disentangle subtle planetary signals from dominant stellar noise (jitter). This work implements a dual-framework approach to determine the mass and density of TOI-4399 b using:
- **Space-based Photometry:** TESS (4 sectors) and CHEOPS (1 targeted visit).
- **High-Precision Spectroscopy:** 150 individual observations from HARPS (ESO 3.6m).

### Key Results
- **SCALPELS Failure Analysis:** Demonstrated the "Parity Filter" effect, explaining why linear morphological filters fail to mitigate jitter in fast rotators.
- **MDGP Modeling:** Applied a Multi-Dimensional Gaussian Process (MDGP) via `PyANETI` to recover a planetary semi-amplitude $K \approx 7.05$ m/s ($M_p \approx 23.1 \ M_\oplus$).
- **The Density Puzzle:** Identified an 8-$\sigma$ tension between the photometric stellar density ($\sim 4.7$ g/cm³) and the spectroscopic G0V primary.
- **Scenario B:** Proposed a host-star swap hypothesis (unresolved M-dwarf background star) as the most physically consistent solution.

## 📂 Repository Structure

The repository is organized to follow the logical flow of the thesis analysis:

- `photometry/`: Jupyter Notebooks for TESS detrending (`wotan`) and CHEOPS multi-parametric simultaneous fit.
- `spectroscopy/`: Modular implementation of the `SCALPELS` algorithm, featuring SVD decomposition and LOOCV rank selection.
- `mdgp_pyaneti/`: Input configuration files and posterior post-processing for the `PyANETI` Bayesian framework.
- `results/`: High-resolution diagnostic plots, corner plots, and final parameter tables.
- `scripts/`: Helper functions for flux dilution calculations and Scenario B1 scaling relations.

## 🛠️ Main Dependencies

To reproduce the analysis, the following Python packages are required:
- `numpy`, `pandas`, `matplotlib`, `scipy`
- `astropy` (Astrometry and constants)
- `batman-package` (Transit modeling)
- `lmfit` (Non-linear optimization)
- `lightkurve` & `wotan` (Light curve processing)
- `PyANETI` (Multi-dimensional Gaussian Processes)

## 📜 License

This project is licensed under the **GPL v3.0 License** - see the [LICENSE](LICENSE) file for details.

## ✍️ Citation

If you use this code or the results for your research, please cite the original work:

> **Maschietti, G. (2025).** *Digging in the stellar noise: photometric and Doppler analysis of the young transiting system TOI-4399.* Master's Thesis, Università degli Studi di Torino.

## 📧 Contact

For specific queries regarding the implementation of the **Parity Filter** analysis or the **MDGP calibration**, please contact:
**Giampaolo Maschietti** - giampaolo.maschietti@edu.unito.it
