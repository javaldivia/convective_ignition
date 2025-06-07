# Experimental Data Description

This folder contains the file `exp_data.csv`, which includes processed experimental results from ignition tests. Below is a description of each column.

## Column Descriptions

| Column Name                 | Units         | Description                                                                 |
|-----------------------------|---------------|-----------------------------------------------------------------------------|
| Experiment                  | —             | Identifier or index of the experiment.                                     |
| Name_tag                   | —             | Descriptive tag for the experiment. `N` or `D` refer to the drying mechanism, `T` is temperature, and the number is the replicate ID         |
| Date                        | YYYY-MM-DD    | Date of the experiment.                                                    |
| N_or_D                      | —             | Indicates whether the sample was *naturally* dried (N) or *forced* dried (D).                |
| TC_corrected                | °C            | Average corrected thermocouple temperature.                                |
| sd_TC                       | °C            | Standard deviation of the corrected TC temperature.                        |
| Vel                         | m/s           | Average flow velocity measured before the experiment.                      |
| sd_vel                      | m/s           | Standard deviation of the flow velocity.                                   |
| ignition_type               | —             | Type of ignition observed. `FI`: flaming ignition, `NI`: no ignition                         |
| ign_code                    | —             | Categorical code assigned to the ignition type (`FI` = 1, `NI` = 0)                            |
| glowing_time                | s             | Duration of glowing before flaming                   |
| t_ig                        | s             | Time to ignition (from exposure start to flaming).                         |
| max_flame_height_cm         | cm            | Maximum observed flame height during the experiment.                       |
| Gas_phase_ign               | Boolean       | Indicates if gas-phase ignition occurred (`True` or `False`).              |
| Gas_phase_ign_loc_cm        | cm            | Location (vertical) where gas-phase ignition initiated.                    |
| Gas_phase_flame_speed_mps   | m/s           | Propagation speed of the gas-phase flame.                                  |
| fmc_p                       | %             | Fuel moisture content                                 |
| sd_FMC                      | %             | Standard deviation of FMC.                                                 |

## Notes

- All temperature and velocity values represent time-averaged quantities over the steady-state region.
- FMC is measured using the oven-dry method.
- For experiments with no flaming ignition, `t_ig` and flame height are left blank or marked accordingly.
- `Gas_phase_ign` is a Boolean indicating whether flame propagation in the gas phase was observed.

[View `exp_data.csv`](./exp_data.csv)
