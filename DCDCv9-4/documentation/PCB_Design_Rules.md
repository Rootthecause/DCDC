
This file contains some additional info on the build guide.

# General design rules
- Function over (optical) design
- Mind the power losses:
    - Choose components and topology as efficient as practical.
    - Make current carrying traces/planes as wide as possible for low resistance.
    - Be aware of the physical PCB stackup:
        - How many OZ Copper on which layer?
        - How thick are prepreg and core materials?
    - Mind parasitics (inductive/capacitive) of traces/planes.
    - Allow good thermal sinks for components that generate heat.
- Figure out, what component values are important and add some safety margin.<br>
Buy the cheapest product that fulfils these requirements from an established manufacturer.
- Don't cheap out at components, which are imporant for safety, reliability, efficieny or performance.
- If in doubt ~~leave it out~~ do simulations.
- If simultaions are inaccurate or too time consuming, try building the real thing and probe your signals. But always remember "Wer misst, misst Mist".
- RTFM (exclamation mark)

## Spacing (IPC 2221 B4) and fillet radius
| Potential between two wires | Spacing required outer/inner| Spacing used outer/inner| fillet radius                | used for                     
|:---------------------------:|:---------------------------:|:-----------------------:|:----------------------------:|:----------------------------:|
| ≤ 100 V                     | 0.050 / 0.1 mm              | 0.2 / 0.2 mm            | 0.5 mm                       | 24 V and Signals             |
| ≤ 150 V                     | 0.400 / 0.2 mm              | 0.4 / 0.2 mm            | 1.0 mm                       | Secondary side rectification |
| ≤ 630 V                     | 1.197 / 0.575 mm            | 1.2 / 0.6 mm            | 1.0 mm                       | HV input                     |
| any to edge cut             |       -                     | 0.3 / 0.3 mm            |   -                          |                              |

## Trace width Rules (IPC 2221)
All currents for 5 k Temp increase @ 1 OZ Copper 
| Trace width  | outer layer | inner layer  |
|:------------:|:-----------:|:------------:|
| 0.25 mm      |   0.63 A    | 0.32 A       |
| 0.30 mm      |   0.72 A    | 0.36 A       |
| 0.40 mm      |   0.88 A    | 0.44 A       |
| 0.50 mm      |   1.05 A    | 0.52 A       |
| 0.75 mm      |   1.41 A    | 0.70 A       |
| 1.00 mm      |   1.74 A    | 0.87 A       |
| 1.20 mm      |   1.98 A    | 0.99 A       |
| 2.00 mm      |   2.87 A    | 1.43 A       |
| 3.00 mm      |   3.86 A    | 1.93 A       |
| 4.00 mm      |   4.75 A    | 2.37 A       |
| 5.00 mm      |   5.59 A    | 2.79 A       |

Note: Wider traces may be used to decrease parasitic Inductance and reduce losses.<br>
As a general rule, choose traces as wide as possible for the given space.

## PCB Requirements (for best performance)
- 4-Layer PCB
- 1.6 mm (standard) thickness
- 2 OZ outer Copper, min. 0.5 OZ inner copper (2 OZ for inner layers would be best but are expensive, therefore inner layers are less used for high currents here)
- TG 135 or higher
- matte back PCB Mask performs best for emissivity 
- filled & capped Vias would be best, but plugged ones did not cause any issues so far
- Used Via Size: 0.4 mm hole diameter, 0.8 mm annular ring
- HASL Leaded or unleaded? Both work fine, but for EU better get the unleaded one

## KiCAD Notes
- if the plugin "Fabrication Toolkit" is used, make sure to update pcb from schematic in order to generate an up to date BOM
- special characters like "µ" and "Ω" are not supported by JLC's BOM reader. Be sure to aviod them, otherwise it will be unable to find replacement parts
