# Lauritzen-Hoffman Theory for Polymer Crystallization

## Overview
This package computes **secondary nucleation constants** from **DSC (Differential Scanning Calorimetry)** measurements (Enthalpy vs. Time) using the Lauritzen-Hoffman theory. 

📄 [Theory and Background](https://nvlpubs.nist.gov/nistpubs/jres/64A/jresv64An1p73_A1b.pdf)

## Features
- Analyze DSC data to calculate **secondary nucleation constants**.
- Fit experimental data using the Lauritzen-Hoffman growth model.
- Output key parameters such as the **secondary nucleation constant** (`kg`) and the **logarithm of the pre-exponential factor** (`lgI0`).

---

## Installation
Install the package using pip:

```bash
pip install lauritzen-hoffman
```

---

## Example Usage

### Import the Module
```python
from lauritzen_hoffman.linear_rate import lh_growth_model
```

### Input Parameters
1. **`file_path:`** Path to your DSC (Differential Scanning Calorimetry) measurement file.
2. **`initial_guess:`** Initial guess values for optimization.
3. **Constants and Data:**
   - `Area`: Crystalline surface area used in calculations.
   - `T_range`: List of temperatures at which growth is analyzed.
   - `U`: Activation energy for transport.
   - `Tinf`: Temperature below which molecular motion stops.
   - `T0m`: Equilibrium melting temperature.
   - `R`: Universal gas constant.

### Example Code
```python
from lauritzen_hoffman.linear_rate import lh_growth_model

# Define file path to your DSC data
file_path = 'path_to_your_dsc_data.csv'

# Set initial guess for the fitting parameters
initial_guess = [value1, value2, ...]

# Define constants and conditions
Area = 1.300149 * (10 ** -12)  # Example area in square meters
T_range = [T1, T2, T3, ...]   # List of temperature values in Kelvin
U = your_value                 # Activation energy for transport (e.g., kJ/mol)
Tinf = your_value              # Theoretical temperature below which no motion occurs (Kelvin)
T0m = your_value               # Equilibrium melting temperature (Kelvin)
R = 1.99                       # Universal gas constant (J/(mol*K))

# Run the Lauritzen-Hoffman model
kg, lgI0 = lh_growth_model(file_path, initial_guess, T_range, Area, U, R, Tinf, T0m)

# Results
print("Secondary nucleation constant, kg:", kg)
print("Logarithm of pre-exponential factor, lgI0:", lgI0)
```

---

## Parameters
- **`file_path:`** Path to the DSC measurement file.
- **`initial_guess:`** A list of initial guesses for the parameters being optimized.
- **`Area:`** Crystalline surface area (default example: `1.300149 * (10 ** -12) m²`).
- **`T_range:`** List of temperature values (Kelvin).
- **`U:`** Activation energy for molecular transport.
- **`Tinf:`** Temperature below which molecular motion stops.
- **`T0m:`** Equilibrium melting temperature (Kelvin).
- **`R:`** Universal gas constant (J/(mol*K)).

---

## Outputs
The function computes:
1. **`kg:`** The secondary nucleation constant.
2. **`lgI0:`** Logarithm of the pre-exponential factor.

