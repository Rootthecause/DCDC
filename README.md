[![kicad](https://img.shields.io/badge/KiCad-8.0.5-1F4FFF)](https://www.kicad.org/)
[![LTspice](https://img.shields.io/badge/LTspice-17.0-910029)](https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html)

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
|September 15, 2025| **IMPORTANT NOTICE**: There was a complaint about the converter not being rules conform. Due to other personal priorities it might take some weeks to solve the adressed points. There is also the chance of some points unable to be solved. See #10 for further details.|
| August 6, 2025 | Announcing the v10 development - ideas welcome! Read more [here](https://github.com/Rootthecause/DCDC/discussions/9). DCDCv10 [survey](https://forms.gle/ou8AZbYJj4cU9K3A8).|
| July 18, 2025 | bad F_min setting lead to repeatable FET destruction, please re-read the Build Guide Pages 35/36 if you've set up your replica before this change. See [issue#8](https://github.com/Rootthecause/DCDC/issues/8) |
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

# VERSION HISTORY

|Version| Changes |
|:---------------------:|:--------------|
|<strong>v0</strong>		|Initial Idea: November 2019 |
|<strong>v1 - v4	</strong>|	2020 - 2021 Just theoretical approaches at design and simulation stage.|
|<strong>v5</strong>	|Jan. 2022, Fist manufactured PCB, very flawed, take it as a lecture on how to NOT do things.|
|<strong>v6</strong> |Feb. 2022, Should have been a improved version to v5, however v5 was so flawed, that simple improvements wouldn't be enough. Ultimately this version was scrapped entirely.|
|<strong>v7</strong> | April 2022, A complete redesign done in two weeks, making it almost 30% smaller. However, a new approach (using a gate driver transformer) proved to be a bad idea, allowing only for 150W at 600V. After removing the gate driver transformer and installing a UCC21520 as gate driver, the power level tripled without any other modifications. When further flaws were found and fixed, the converter was able to deliver 1525W for 10 seconds at 92.7% efficiency. After that, the highest component temperature was 85°C (diodes), suggesting that even longer operation at this power would be possible. However further tests were never done, because the power sink was at its limit and in-vehicle tests had to be performed. |
|<strong>v8</strong>	|	July 2022, The 2-layer PCB was reworked as 4-layer design with new knowlegde on "black magic" in mind, reducing EMI and parasitic inductances. This opened up new layout possibilities, making the over all design more compact and cleaner. Several bugs were fixed, making this version the first successful design. Also it was the first version, featuring active rectification. The maximum Power was just around 1000W for a few seconds, since a smaller transformer was used, making it by far the hottest part on the PCB. As a fix, a 30mm fan was mounted to it.|
|<strong>pre v9</strong>	|	Okt. 2022, A v8 PCB was equipped with components planned for the 9th version. The main point of this Version was to adress the "hot transformer issue". After discussion with a knowlegable person, the "m-Value" was to found to be understood in a opposite way, leading to flawfully choose the worst value. This issue existed ever since. However, tests with a higher "m" value showed, that the effect does not sigificantly reduce the heat. Instead, the focus has shifted toward different types of transformer power losses. It seems that the proximity effect could be the main problem. If this can be solved, the efficiency could reach new records and eliminate the need for a transformer fan, which would further increase efficiency.|
|<strong>v9</strong> |	Jan. 2023, Although the 8th version (3rd PCB) of this converter was already very successfull and operates since august of 2022 in a race car, there were smaller issues discovered (see pre v9). The 9th version aims to fix those issues as well as making it reliable in the long run, reducing costs by minimizing overhead and optimizing the schematic. The new PCB is 33% smaller and has the size of one credit card.|
|<strong>v9-2</strong> |	May 2024, Fixes an issue with high startup currents due resonace with magnetising inductor of the transformer by adding external soft start. A new script allowed for calculate proximity losses to find the ideal HF-litz wire. Different transformer coil designs have been tested and an theoretical optimal solution has been found with good real world perfomance, allowing for high gain operation, therfore increasing input voltage range from 400-600 V to 200-600 V. The footprint was redesigned making it more space efficient but also allowing for more "air to breath". The new design is optimized for 24V output voltage. Other Voltages (12V/36V/48V) are Possible as well, but may need different capacitors and HEMETs. Adjust number of secondary turns accordingly! Using the "GaNdalf 1.0" extension PCB, GaN HEMETs have been used for the first time for active rectification on the v9 board. The results were promising, although tests could not been cerried out as hoped, since unexpected breakdowns occured (eliminating available stock). A possible issue was found and adressed. The v9-2 PCB can use up to two parallel HEMETs per half wave. Unfortunatley an inherent issue with ringing was discovered, leading to false triggering and destruction of the HEMETs. Some solutions were tested, allowing for up to 300W at 96.9% efficiency (one HEMET per half wave), but due to the way smaller size of the chips, additional cooling was needed. Using a small Heat sink and TIM broke both HEMETs and destroyed the footprint. This incident and the already very difficult process of replacing the HEMETs led to the use of MOSFETs again. Another issue was found: The 12V step-up IC was unable to provide enough current at temperatures above 65°C when the half bridge had to start. As a fix additional capacitors where installed. It was found out later, that the particular IC was not a good choice in general and will be replaced in v9-3. 
|<strong>v9-3</strong> |	DOES NOT USE the updated gate driver (UCC21550), which (unfortunately) runs on 5V instead of 12V but is readily available and less than halve the price, because the needed changes are not worth the hustle and there are still more than 15k Avaiable on Mouser (Summer 2024). I belive untill the stock is zero the v10 might be released, which would be easy to implement there. Gate driver capacitors were changed according to datasheet and simplified. Split resonant capacitors are used which reduce peak voltage ripple by a factor of 3.5. Hence DC Link cap could be reduced from 7 µF to 2 µF. The TL431 received a own 9V stabilized Voltage source from a LDO for enhanced 12V ripple rejection and better tempco. A lot of research has been done to find new MOSFETs for synchronous rectification (SR) that are smaller and have much lower losses than those previously used (this has yet to be proven by tests). If everything goes according to plan, the peak power could be increased beyond the currently approved 600 W. |
|<strong>v9-3r</strong>		| This is the release version for the public open source release. Small improvements have been made with buffer capacitors in the LV power supply to increase performance when using larger fans. When measuring the ripple voltage at the output, 1.5 Vpp voltage peaks were measured, which were  associated with the step-down. Nevertheless, the exact cause is still unclear. The problem could be mitigated almost down to the measurement noise by using 1 nF capacitors and snubbers over certain components. The footprint for the 9 V LDO has been adjusted as the originally intended model is not available. The lowpass on the CS pin of the SR drivers was changed from 47 Ω / 470 pF to 100 Ω / 1 nF for more reliable triggering. The secondary-side snubbers were marked as DNP, as they were no longer necessary in tests (lowpass also acts as a snubber). The HV input connector was rotated 180° on the PCB. |

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
Send me a DM on [Reddit](https://www.reddit.com/user/Rootthecause/) with a photo of your replica.  
Thanks!