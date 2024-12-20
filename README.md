## Lauritzen_Hoffman theory for polymer crystallization

Package for computing secondary nucleation constants from DSC measurements Enthalpy vs time
[link](https://nvlpubs.nist.gov/nistpubs/jres/64A/jresv64An1p73_A1b.pdf)
# Installation
```
pip install lauritzen-hoffman

```
```
# Example usage
```
from lauritzen_hoffman.linear_rate import lh_growth_model

file_path = 'file_path'
initial_guess = your values 
Area = 1.300149 * (10 ** (-12))
T_range = [T1, T2,..]
U = your value
Tinf = your value (kelvin)
T0m = your value (kelvin)
R = 1.99

kg, lgI0 = lh_growth_model(file_path, initial_guess, T_range, Area, U, R, Tinf, T0m)

