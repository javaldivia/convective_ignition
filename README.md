# 🔥 Glowing to Flaming Transition of Douglas Fir with Varied Moisture Content

This repository contains the datasets, models, and simulation files developed for the study:

**"Glowing to flaming transition of Douglas fir with varied moisture content"**  
Published in *Fire Safety Journal*, 2025.

If you find these tools useful, please cite our work:

```bibtex
@article{Valdivia2025,
  title   = {Glowing to flaming transition of Douglas fir with varied moisture content [manuscript accepted for publication]},
  journal = {Fire Safety Journal},
  year    = {2025},
  author  = {Jorge Valdivia and Xiuqi Xi and Albert Simeoni and James L. Urban}
  }
```

The `doi` will be provided once available.

More information about the authors:  
> **Jorge Valdivia** [![ORCID](https://img.shields.io/badge/ORCID-0009--0003--4251--1108-a6ce39?logo=orcid&style=flat-square)](https://orcid.org/0009-0003-4251-1108) <br>  
> **Xiuqi Xi** [![ORCID](https://img.shields.io/badge/ORCID-0000--0003--3245--232X-a6ce39?logo=orcid&style=flat-square)](https://orcid.org/0000-0003-3245-232X) <br>  
> **Albert Simeoni** [![ORCID](https://img.shields.io/badge/ORCID-0000--0002--5497--3794-a6ce39?logo=orcid&style=flat-square)](https://orcid.org/0000-0002-5497-3794) <br>  
> **James L. Urban** [![ORCID](https://img.shields.io/badge/ORCID-0000--0002--2476--8212-a6ce39?logo=orcid&style=flat-square)](https://orcid.org/0000-0002-2476-8212) <br>  


---

## 📦 Repository Version

- **Version**: 1.0.0  
- **Release Date**: May 19, 2025  
- **Changelog**: Initial release

---

## 📁 Repository Structure

- `ignition_data/` — Experimental data (time to ignition, FMC, thermocouple, flow)
- `thermal_model/` — Thermal decomposition model (Python)
- `gas_phase_ignition/` — Flame tracking and propagation speed estimation
- `numerical_simulation/` — FDS input files, postprocessing, and results

---

### 1. Ignition Data

- Time-to-ignition measurements for Douglas fir samples under hot convective flow.
- Includes statistical analysis of ignition probability as a function of gas temperature and fuel moisture content (FMC).
- Contains logistic regression to identify the critical gas temperature ($T_{gas,cr}$) for 50% ignition probability.
- Evaluates the duration between glowing combustion and flaming ignition ($\Delta t = t_{ig} - t_{glow}$).

**Notebook:** [`ignition.ipynb`](ignition.ipynb)

### 2. Thermally controlled ignition model

- Implements a 0D transient energy balance on a pine needle (cylindrical element) under convective flow.
- Includes convective heating, radiative input from plenum walls, and radiative losses.
- Uses experimentally derived parameters (e.g., gas temperature, flow velocity, surface area).
- Predicts ignition delay time for a critical solid temperature ($T_{s,cr}$).
- Results are compared with experimental measurements for validation.

**Notebook:** [`thermal-model.ipynb`](thermal-model.ipynb)

### 3. Gas Phase Ignition and Flame Propagation

- Code to detect gas-phase ignition kernel and estimate vertical flame velocity
- Analyzed using OpenCV on high-speed video recordings

### 4. Numerical Simulation (FDS)

- FDS v6.9.1 simulations using the spark ignition model
- Includes geometry, boundary conditions, Lagrangian fuel particles, and post-processing tools


---

## 📊 Reproducibility

All code was tested using:
- Python 3.13
- FDS 6.9.1

---

## 📄 License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This repository is licensed under the [MIT License](LICENSE).
You are free to use, modify, and distribute this code, provided that proper credit is given.  
If you use this repository or parts of it, please also cite our related publication.

---

## 📫 Contact

For questions, suggestions, or collaboration inquiries, please open an issue or contact the corresponding author listed in the paper (James Urban, [**jurban@wpi.edu**](mailto:jurban@wpi.edu)), or the first author (Jorge Valdivia, [**javaldivia@wpi.edu**](mailto:javaldivia@wpi.edu)).
