# Caravel Analog User

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![UPRJ_CI](https://github.com/efabless/caravel_user_project_analog/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_user_project_analog/actions/workflows/user_project_ci.yml) [![Caravan Build](https://github.com/efabless/caravel_user_project_analog/actions/workflows/caravan_build.yml/badge.svg)](https://github.com/efabless/caravel_user_project_analog/actions/workflows/caravan_build.yml)

---

# [Google Skywater 130nm](https://github.com/google/skywater-pdk) Comparator IP

## Introduction
A comparator is a device that compares two analog inputs and outputs a digital signal indicating which input is larger. So it has two analog input terminals and one binary digital output. 
When the difference between two analog input signals approach zero, noise on the inputs will cause spurious switching of digital output. This rapid change in output due to noise can be prevented by hysteresis. Hysteresis is switching the output high or low at different input signal levels. In place of one switching point, hysteresis introduces two: one for rising edge, and one for falling edge of voltage or current. The difference between the higher-level trip value (VH) and the lower-level trip value (VL) equals the hysteresis voltage (HYST).

### Inputs to the circuit
1. VCC - 3.3 v
2. GND - Ground
3. INN - Negative differential input
4. INP - Positive differential input
5. EN  - Enable pin
6. Ihyst - Current to control hysteresis

### Output of the circuit
1. VOUT - Comparator output

### Circuit details
A comparator can be divided into three distinctive pieces – a frontend differential amplifier, amplifier stage and output stage.

This comparator consists of
1. Frontend differential amplifier
2. Amplifier of the output from frontend differential sage
3. NAND gate to act as buffer as well as incorporate the enable pin
4. Inverter to act as final buffer before output. The NAND and Inverter improves the slew and provides a little gain.
5. Positive feedback differential set-up. 

This is very similar to set-up on [2] but I have added some modifications to incorporate ENable pin and improve the performance on SKY130 PDK.

## References
1. P. Horowitz,and W. Hill, “The Art of Electronics,” Cambridge Press University, 3rd ed (references) 
2. P. Furth, Y. Tsen, V. Kulkarni,and T. Raju, On the Design of Low-Power CMOS Comparators with Programmable Hysteresis., IEEE, 2010, pp.1077–1080.

