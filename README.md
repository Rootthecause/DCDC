[![kicad](https://img.shields.io/badge/KiCad-8.0.5-1F4FFF)](https://www.kicad.org/)
[![LTspice](https://img.shields.io/badge/LTspice-17.0-910029)](https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html)
[![Discord](https://img.shields.io/badge/DCDC_Discord_Server-7289da)](https://discord.gg/3PkHGpJvR4)


![](https://github.com/Rootthecause/DCDC/blob/main/documentation/pictures/header.png?raw=true)

Dear Formula Student Teams,

I've designed a High Voltage DC/DC Converter to replace our LV Battery. Feel free to use it as well!<br>
Although this design (and previous versions) have passed two times FSG scrutineering and have been operating without any issues for over 6 months*, <strong>always manufacture at your own risk!</strong><br>
If you encountered any bugs or have suggestions for improvement, please use the GitHub [issues form](https://github.com/Rootthecause/DCDC/issues/new). For discussions and technical questions, kindly use the [discussion bord](https://github.com/Rootthecause/DCDC/discussions).<br>

This design is published as open-source hardware under the CERN-OHL-W license and can be found on GitHub: https://github.com/Rootthecause/DCDC<br>
If you had early access to this GitHub page or received any files from me directly, please do not share or publish them, as I don't want others to share files which may be incomplete or contain errors.<br>

Have fun! Do not lick things with spark symbols on :) 

Best regards,
Rootthecause / Liv 

<br>

# Updates
|Date | Description |
|:---------------------:|:------|
|January 29, 2026| First public v10 schematic, see [v10 development](https://github.com/Rootthecause/DCDC/discussions/9#discussioncomment-15634156), also contains a timeline and small v9-3 update|
|January 4, 2026| New year's update on [v10 development](https://github.com/Rootthecause/DCDC/discussions/9#discussioncomment-15400450) |
|November 30, 2025| Update on [v10 development](https://github.com/Rootthecause/DCDC/discussions/9#discussioncomment-15114408), added [![Discord](https://img.shields.io/badge/Discord_Server-7289da)](https://discord.gg/3PkHGpJvR4) for faster communication.|
|September 15, 2025| **IMPORTANT NOTICE**: There was a complaint about the converter not being rules conform. Due to other personal priorities it might take some weeks to solve the addressed points. There is also the chance of some points unable to be resolved for the Version 9-3r. See [issue#10](https://github.com/Rootthecause/DCDC/issues/10) for further details.|
| August 6, 2025 | Announcing the v10 development - ideas welcome! Read more [here](https://github.com/Rootthecause/DCDC/discussions/9). DCDCv10 [survey](https://forms.gle/ou8AZbYJj4cU9K3A8).|
| July 18, 2025 | *bad F_min setting lead to repeatable FET destruction, please re-read the Build Guide Pages 35/36 if you've set up your replica before this change. See [issue#8](https://github.com/Rootthecause/DCDC/issues/8) |
<br>

# Important documents
|File | | |
|:---------------------:|:--------------:|:------:|
| Documentation [PDF] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/documentation/Documentation_DCDCv9-3r_EN.pdf)| [GERMAN](https://github.com/Rootthecause/DCDC/blob/main/documentation/Documentation_DCDCv9-3r_GER.pdf)|
| Build Guide [PDF] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/documentation/Build_Guide_DCDCv9-3r_EN.pdf)| [GERMAN](https://github.com/Rootthecause/DCDC/blob/main/documentation/Build_Guide_DCDCv9-3r_GER.pdf)|
| Data sheet [PDF] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/documentation/Datasheet_DCDCv9-3.pdf)|-|
| KiCAD Files| [ENGLISH](https://github.com/Rootthecause/DCDC/tree/main/kicad)|-|
| Schematic [PDF] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/kicad/DCDCv9-3.pdf) |-|
| LTspice Simulation| [ENGLISH](https://github.com/Rootthecause/DCDC/tree/main/ltspice)|-|
| Measurements Table [xlsx] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/documentation/DCDCv9-3_Table.xlsx) |-|
| Scrutineering Support Presentation [PPTX] | [ENGLISH](https://github.com/Rootthecause/DCDC/blob/main/documentation/scrutineering_support_files/DCDCv9-3_Scrutineering_Support_Presentation.pptx)|-|


<br>

# Build Notes v9-3
Please read [here](https://github.com/Rootthecause/DCDC/blob/main/v9-3_build_notes.md) for build errors of a v9-3 replica.

# Note for PCB-Orders
**Always check the latest release before ordering!**
There are new releases for every significant hardware change.
I do not recommend ordering from the latest repro clone, as it might contain unfinished hardware changes. However, simulation files or documents might be more recent.
<br>
<br>
# Who should build this?
This project is for anyone who is keen to build a DC/DC converter for powering low voltage devices from high voltages or for research.
Unfortunately, it's currently not a simple one-day-build (maybe 1-2 days for building and 1-2 Weeks for testing), but I'm working on it, making it as accessible as possible.
The skillset required ranges from soldering SMD components, SLA-Printing to sanding ferrite cores and winding a transformer (sanding is currently not needed anymore).
The documentation not only contains explanations of many components, but also detailed written assembly instructions.
I might also record a few instruction videos if there is a demand.
Stick with it - the results speak for themselves.<br>
<br>
# Technical Specifications

The DCDCv9-3 is a galvanically isolated DC/DC converter, designed to convert voltages from 200 V to 600 V down to 24 V with max. 500 W continuous output power. The low weight of 167 grams and the small footprint of a credit card (85.6 x 54 mm) are well suited to the automotive industry for supplying low-voltage systems from HV Batteries. The dynamic operating frequency between 90 and 200 kHz ensures high efficiency for various loads as well as good EMI compliance due to the resonant LLC soft switching topology. Customized versions allow output voltages from 12 V to 48 V.
<strong>

- Input Voltage Range: 200 to 600 V 
- Designed Output Voltage: 24 V
- max. Output Power (min. 400V):
	- Continous:&ensp;&ensp;&ensp;&ensp;500 W
	- 180 Seconds:&ensp; 600 W
	- 60 Seconds:&ensp;&ensp;&ensp;750 W
- max. continous Output Power at 200V: 300 W
- max. continous Output Power at 300V: 500 W
- Efficiency up to 96.9 % at 500 W load / 500 V input
- Size: 85.6 x 54 mm x 45 mm
- Weight: 167 grams

Features
- built-in solid-state precharge
- active rectification (NCP4305DMTTWG)
- Galvanically isolated enable pins with self recharging start-up capacitor
- undervoltage, overvoltage and overcurrent protection 
- low no-load power dissipation (7W-9W) 
- cost efficient UCC25600 LLC controller
- reliable 4 A/6 A UCC21520 Gate Driver
- onboard HV- and LV fuses
- minimum isolation distance 4.5 mm (According to rule EV 4.3.6, Table 5, Conformal Coating: 600V DC -> min. 4 mm spacing required)
- optional back side connectors for on-PCB mount 
- NOT FULLY FSG-Rules 2025 conform [September 15, 2025 there was a complaint, see #10 for further information. This may or may not resolved in the future.]
</strong>
<br>
<br>

### Future plans

The main goal of this project is to create a universal approach for safe and efficient conversion of voltages.
At the moment, the converter can accept any input voltage up to at least 600V if UVP/OVP and component
Values are chosen correctly. On the output side, the step-down regulator (65V) is the limiting factors. 
A VIPER06 IC could be used to achieve HV stepdown, or depending on the input voltage, 
the stepdown could be could be shifted to the input side. This could also allow a self-starting converter to 
be used as an SMPS in combination with a PFC. Another approach would be a bidirectional design so that the 
stepdown is on the lower voltage side. Since active rectification is already implemented, bidirectional 
conversion could be possible given the right IC. With the current development and rise of GaN MOSFETs, 
a converter with PCB transformer in the MHz range might also be possible.


# Do's and dont's 
## General
- Not as much as possible, but as much as needed (words from a friend).
- If you don't test to the limits, you don't know where they are.
- Always start with low Voltage/Power and slowly increase it.
- Figure out what measurements and values (step size) are important.
- If issues appear, try to solve them sooner than later - but depending on type, they can be an oppurtunity to test out limits.
- avoid making too many changes at once (except you want to perform multivariant testing), or be sure that the changes do not affect each other

## Project specific
- use short traces for anything that has to switch things (PCB design is complex, than that, but keep wire impedance low as well as parasitics)
- make sure, your gate Driver provides clean on-off signals to the MOSFETs. Otherwise you'll blow them up for sure sooner or later. Use MOSFETs with Kelvin connections if possible (and be sure about their correct wiring).
- Do use Gate driver IC's and not Gate Transformes (they suck). If possible, use Isolated Gate Drivers. Thats a good layer of protection if the half bridge blows up.
- Always have a Thermal Camera at hand. There are relatively cheap options as USB-C accessories for Phones (~250€). I use one from TOPDON with an added maco lens. It's worth every penny, not just for a DC/DC but also other FS Stuff. It will help you to find overloaded components (too hot) or non functioning compontens (no heat). Keep in mind, that there might be thermally reflective surfaces (brushed aluminium is like a mirror!). 
- Use your ears and nose in a quite environment while testing. Many issues can be heard (humming, cracking sounds), and some smelled (too hot component).
- Be sure to add test points to your PCB while developing, which can be acessed via jumper wires or simliar. Do not attempt to measure anything directly with a probe while the converter is running, since a small slip can be enough to ruin the whole converter and maybe even do harm to yourself. 
- use an Oscilloscope with Isolated inputs (alternative use differential probes or an battery powered Oscilloscope) to check signals. 


## Replicas
*Last updated: May 9, 2025*

- At least 4 Formula Student teams are replicating the DCDCv9-3r in 2025  
- At least 1 team has successfully built and tested the DCDCv9-3r:  
  - TU Graz Racing, Austria 

<br>

**Want to add your team to this list (publicly or anonymously)?**  
Send me a DM on [Reddit](https://www.reddit.com/user/Rootthecause/).  
Thanks!

## Star History

<a href="https://www.star-history.com/#Rootthecause/dcdc&type=date&legend=bottom-right">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Rootthecause/dcdc&type=date&theme=dark&legend=bottom-right" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Rootthecause/dcdc&type=date&legend=bottom-right" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Rootthecause/dcdc&type=date&legend=bottom-right" />
 </picture>
</a>
<br>
<br>