# Build Notes v9-3

Hi there! 
Over the last months I've received countless questions and issues related to building a v9-3 replica. 
In this document I'll try to address them _cleanly_, so you don't have to dig trough the forum discussions, which unfortunately has gotten somewhat convoluted.

_Please not that I'm using YYMMDD, because I'm sick of other date formats. Old topics go last._

|Date | Title | Description |
|:---------------------:|:------|:------|
|260208|PCBA resistors replaced with milli Ohm instead of mega Ohm| When ordering the PCB with assembled parts (PCBA), the high voltage resistors R1 and R71 in the 2512 package might be not on stock at JLC and therefore repleaced with others with 100 mOhm instead of 100 MOhm. There should be a warning on those components being replaced at the PCBA component selection. Either choose matching resistors (similar Voltage rating, same Resistance and package) or do not place them for PCBA and order at e.g. Mouser instead. A symptom of this is the precharge LED lighting up at initial tests with low voltage at the HV input above around 20V. If this goes unnoticed at higher HV input voltages, breaking U14 might be possible. However, as the precharge is only precharging in this state, the max. input current is limited to 5.5 mA 😄|
|260100|Measuring Lp and Lr correctly|To measure those values, you don't need an expensive Analog discovery. A cheap LCR-Meter works well enough in most cases (I've done so for years before I got the AD2). The donwnside is, that cheap LCR meters might measure based on resonant frequency, which depends on inductance. If it is measured at 350 kHz expect around 1% of increase of inductance from my measurements at 100 kHz. Measurements down to 10 kHz usually do not differ much from those at 100 kHz. If you're measuring Lr, make sure to short only one of the secondary coils. Use a alligator clip to directly short / press both ends of a secondary together - DO NOT use a cable inbetween both ends, as the length of the cable (even a few centimeters) will increase the inductance value significantly! Also keep the cables from the LCR Meter very short and apply open-short compensation.|
||||
<br>


