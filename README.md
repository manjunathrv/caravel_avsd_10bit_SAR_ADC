# Caravel User Project

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![UPRJ_CI](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml) [![Caravel Build](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml)

Table of contents
=================
<!--ts-->
   * [Project Description](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-1)   
   * [Specification](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
   * [References](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
<!--te-->


# Project Description

In this work, the design and implementation of a 10-bit Successive Approximation Register(SAR) Analog to Digital Converter using Skywater 130nm CMOS is presented. </br>

A block diagram of the 10-bit SAR ADC architecture used in this work is shown below.

   <p align="center">
   <img src="/docs/Images/SAR_Block_diagram.png" width="80%" height="80%">
   </p>

   </p>

The main blocks of the SAR ADC are, sample and hold (S/H), comparator, Digital to Analog Converter(DAC), SAR and a logic controller. 
During the first clock cycle obtained from the timing controller, the analog input is sampled. 
The sampled output is compared with the half of the reference voltage (Vref/2) obtained from the DAC block to form the first MSB. 
Based on the output obtained from the comparator, the SAR logic block will set the input bits of the DAC to generate the relevant reference signal for the next comparison process.
The comparator continues to compare the input analog signal until the output converges to resolve the last bit.

# Specification

The 10bit ADC target specification are mentioned in the below table[1], </br>

| Parameter  | Description  | Min | Max | Typ | Unit | Conditions |
|----- |-----|-----|
| VDDA | Analog Supply Voltage | 0 | 3.3 | 3.3 | V | Temp = -40 degC to 125 degC|
| VDD  | Digital Supply Voltage | 0 | 1.8 | 1.8 | V | Temp = -40 degC to 125 degC|
| VREFH | Reference Voltage High | 0 | 3.3 | 0 | V | Temp = -40 degC to 125 degC|
| VREFL | Reference Voltage Low | 0 | - | 0 | V | Temp = -40 degC to 125 degC|
| RES | Resolution | - |- | 10 | Bits | Temp = 27 degC|
| INL | Integral Non-Linearity |- | -| +/-1.5 | LSB | Temp = 25 degC|
| DNL | Differential Non-Linearity | - | - | +/-1.5 | LSB | Temp = 25 degC|
| TCONV | Conversion Time | - |- | 12 | Clock Cycles | Temp = 27 degC|


# References
[1] 



Refer to [README](docs/source/index.rst) for the project documentation. 
