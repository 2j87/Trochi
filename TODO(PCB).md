# TODO (PCB)

Remaining PCB-side tasks for the Trochi mainboard.

## 1. Board Outline & Shield Mounting

- [ ] Define board outline matching the ESP32-S3 SuperMini shield footprint
- [ ] Place mounting holes
- [ ] Reserve keep-out area for the SuperMini module footprint

## 2. Component Placement

- [ ] Place all components per schematic groupings (power, motors, IMU/SD, receiver, indicators)
- [ ] Keep motor driver MOSFETs close to their respective connectors
- [ ] Keep IMU away from motor drivers and high-current traces to minimize noise coupling

## 3. Routing

- [ ] Route power traces (VBAT, +3.3V) with adequate width for current
- [ ] Route SPI bus (IMU & microSD) as short, matched-length as practical
- [ ] Route motor PWM and receiver signal traces
- [ ] Run DRC and resolve all violations

## 4. Copper Pours & Silkscreen

- [ ] Add ground plane (copper pour) on appropriate layer(s)
- [ ] Add silkscreen labels for connectors, test points, and polarity markers

## 5. Manufacturing Outputs

- [ ] Generate gerber and drill files
- [ ] Export BOM
- [ ] Export pick-and-place file
