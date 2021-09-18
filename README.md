# Caravel User Project

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![UPRJ_CI](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml) [![Caravel Build](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml)

Table of contents
=================
<!--ts-->
   * [Project Description](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-1)   
   * [Specification](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
   * [Successive Approximation Register and logic controller](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
      * [2-Bit SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#introduction-to-low-power-design)
      * [8-Bit SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#background)
      * [10-Bit SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#background)
   * [Digital to Analog Converter](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
      * [4-Bit DAC](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#introduction-to-low-power-design)   
   * [Integrating DAC with SAR Controller](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
      * [4-bit DAC and SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#introduction-to-low-power-design)   
   * [Integrating DAC and Comparator with SAR Controller](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#day-2)
      * [4-bit DAC, Comparator and SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#introduction-to-low-power-design)
      * [10-bit DAC, Comparator and SAR](https://github.com/manjunathrv/VSD_Low_power_Design_using_Sky130nm_PDK#introduction-to-low-power-design)   
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
|----- |-----|-----| ---- |-----|-----|-----|
| VDDA | Analog Supply Voltage | 0 | 3.3 | 3.3 | V | Temp = -40 degC to 125 degC|
| VDD  | Digital Supply Voltage | 0 | 1.8 | 1.8 | V | Temp = -40 degC to 125 degC|
| VREFH | Reference Voltage High | 0 | 3.3 | 0 | V | Temp = -40 degC to 125 degC|
| VREFL | Reference Voltage Low | 0 | - | 0 | V | Temp = -40 degC to 125 degC|
| RES | Resolution | - |- | 10 | Bits | Temp = 27 degC|
| INL | Integral Non-Linearity |- | -| +/-1.5 | LSB | Temp = 25 degC|
| DNL | Differential Non-Linearity | - | - | +/-1.5 | LSB | Temp = 25 degC|
| TCONV | Conversion Time | - |- | 12 | Clock Cycles | Temp = 27 degC|


# Successive Approximation Register and logic controller 

## 2-Bit SAR
   <p align="center">
   <img src="/docs/Images/2-Bit_SAR.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/2-Bit_SAR_1.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/2-Bit_SAR_2.PNG" width="60%" height="60%">
   </p>

   </p>

## 8-Bit SAR

   <p align="center">
   <img src="/docs/Images/8-Bit_SAR.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/8-Bit_SAR_1.PNG" width="60%" height="60%">
   </p>

   </p>

## 10-Bit SAR

   <p align="center">
   <img src="/docs/Images/10-Bit_SAR.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/10-Bit_SAR_1.PNG" width="60%" height="60%">
   </p>

   </p>


# Digital to Analog Converter 

## 4-Bit DAC

   <p align="center">
   <img src="/docs/Images/4-Bit_DAC.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/4-Bit_DAC_1.PNG" width="60%" height="60%">
   </p>

   </p>

# Integrating DAC with SAR Controller
## 4-bit DAC and SAR 

   <p align="center">
   <img src="/docs/Images/4-Bit_DAC_SAR.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/4-Bit_DAC_SAR_1.PNG" width="60%" height="60%">
   </p>

   </p>


# Integrating DAC and Comparator with SAR Controller
## 4-bit DAC, Comparator and SAR 
   <p align="center">
   <img src="/docs/Images/4-Bit_DAC_SAR_CMP_1.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/4-Bit_DAC_SAR_CMP_2.PNG" width="60%" height="60%">
   </p>

   </p>



## 10-bit DAC, Comparator and SAR 

   <p align="center">
   <img src="/docs/Images/10-Bit_DAC_SAR_CMP_1.PNG" width="60%" height="60%">
   </p>

   </p>
   
   <p align="center">
   <img src="/docs/Images/10-Bit_DAC_SAR_CMP_2.PNG" width="60%" height="60%">
   </p>

   </p>



# Layout design 
## Comparator
   <p align="center">
   <img src="/docs/Images/Comparator.PNG" width="60%" height="60%">
   </p>
   
## SAR
   <p align="center">
   <img src="/docs/Images/SAR_Controller.PNG" width="60%" height="60%">
   </p>



# References



Refer to [README](docs/source/index.rst) for the project documentation. 
