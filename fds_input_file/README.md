# FDS Setup: Convective Ignition of Pine Needle

This folder contains the Fire Dynamics Simulator (FDS) input file used to simulate the convective ignition of a Douglas fir branch (modeled as Lagrangian particles). The configuration corresponds to the experimental setup described in the main study.

---

## 📄 File

- `convective_ignition.fds`: FDS input script defining the computational domain, boundary conditions, material properties, and ignition model.

---

## 🧱 Domain and Mesh

- Full 3D domain dimensions: 40 cm × 40 cm × 40 cm
- Multiple sub-meshes used to preserve resolution and parallelization efficiency
- Mesh resolution: uniform, with IJK = 32 × 32 × 16 per block

To run individual file from `command prompt`:
```bash
cd file_directory
fds_local -p 16 convective_ignition.fds
```

---

## 🌡️ Boundary Conditions

- Hot gas inflow temperature: matched to experimental conditions (e.g., 400–500 °C). Variable: `TMP_FRONT`
- Inlet velocity: 2.41 m/s
- All sides: open boundaries except floor
- Flow mimics conditions from the Convective Ignition Facility (CIF)

---

## 🌿 Fuel Model

- Vegetation represented as cylindrical Lagrangian particles
- Fuel: pine needle with properties derived from experiment and TGA
- Surface-to-volume ratio (SVR): 3940 m⁻¹
- Solid density: 514 kg/m³
- Fuel mass and spatial volume tuned to match experimental branch dimensions
- Moisture content (FMC): variable; specified via initial water mass fraction in the particle definition  
  (values typically between 5% and 85%, consistent with experimental campaigns). Variable: `MOISTURE_FRACTION`
- Moisture evaporation modeled using single-step drying

---

## 🔥 Ignition Model

- Spark model activated using control logic in FDS
- Ignition is triggered when the solid temperature (variable `SETPOINT`) at a control location exceeds a critical threshold (e.g., 370 to 390 °C)
- Autoignition temperature is set locally to 0 K at the spark location; 500 °C elsewhere
- This approach captures the observed glowing-to-flaming transition in the experiments

---

## 💨 Combustion and Chemistry

- Infinitely fast gas-phase combustion model
- Fuel: C₂.₁H₆.₂O₂.₁₆
- Heat of combustion: 17,425 kJ/kg
- Flame radiation fraction: 0.35
- Soot yield: 0.02 (based on wildland fire standards)
- No CO production modeled

---

## ⚠️ Simplifications

- No char oxidation included (to reduce complexity)
- No physical sample holder in the geometry
- Spark model serves as a phenomenological approximation for glowing-to-flaming transition
- Particle insertion delayed by 1 second to replicate the branch insertion into a steady-state hot flow

---

## 📊 Output Fields

- HRRPUV slices near the branch
- Mass loss rate (MLR)
- Flame front development
- Solid temperature of particles

---

## 📝 Notes

- The file is optimized for compatibility with [FDS 6.9.1](https://github.com/firemodels/fds/releases/tag/FDS-6.9.1)
- For validation, ignition delay times and flame development can be compared directly with experimental results and the thermal model

