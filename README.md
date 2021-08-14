# Caravel User Project

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![UPRJ_CI](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/user_project_ci.yml) [![Caravel Build](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml/badge.svg)](https://github.com/efabless/caravel_project_example/actions/workflows/caravel_build.yml)

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

The 10bit ADC target specification are mentioned in the below table[1], </br>

| I/O Pin Name  | V3  | OUT | 
|----- |-----|-----|
| 0(L)  | 0(L) | 1.8(H)|
| 0(L)| 1.8(H) | 1.8(H) |
| 1.8(H) | 0(L) | 1.8(H)|
| 1.8(H)| 1.8(H) | 0(L) |


Parameter	Description	Min	Typ	Max	Unit	Condition
VDDA	Analog Supply Voltage		3.2		V	T=40C to 85C
VDD	Digital Supply Voltage		1.8		V	T=40C to 85C
VREFH	Reference Voltage High			3.3	V	T=40C to 85C
VREFL	Reference Voltage Low	0			V	T=40C to 85C
FCLK	Clock Frequency	0.01	1	2	MHz	T=40C to 85C
RES	Resolution		10		Bits	For all above typical conditions (T=27C)
INL	Integral Non-Linearity				LSB	For all above typical conditions (T=27C)
DNL	Differential Non-Linearity		-14.9		LSB	For all above typical conditions (T=27C)
RIN	Analog Input Resistance		110		kohm	T=-40C - 85C
CL	Analog Input Capacitance				pF	VT=-40C - 85C
IVREF	Current through Reference Source		1.06		mA	For all above typical conditions (T=27C)
T1	Start signal duration		0.5		Clock Cycles	T=-40C - 85C
TCONV	Conversion Time		12		Clock Cycles	T=-40C - 85C
T4	Tracking Time		4		us	T=-40C - 85C
IDDA	Analog Supply Current		2.97619		mA	T=27C, EN=1,FCLK=2MHz
IDDA	Analog Supply Current				pA	T=27C, EN=0,FCLK=2MHz
IDDD	Digital Supply Current		2.833		mA	T=27C, EN=1,FCLK=2MHz





Refer to [README](docs/source/index.rst) for the project documentation. 
