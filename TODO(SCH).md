# TODO

Remaining schematic-side tasks for the Trochi mainboard.

## 1. Power Filtering (Noise Suppression before MCU)

- [ ] Place bulk capacitor (10µF ceramic) on `+3.3V` rail ahead of the SuperMini header
- [ ] Place local decoupling capacitor (100nF) close to the SuperMini `3V3` pin
- [ ] Add ferrite bead between regulator output and MCU supply to isolate motor driver switching noise

## 2. ESP32-S3 SuperMini Header & Pin Assignment

- [ ] Place two 1x8 pin headers (`Conn_01x08`) to mount the SuperMini module
- [ ] Wire net labels per the table below

| SuperMini Pin | Net Label | Function |
|---|---|---|
| 3V3 | `+3.3V` | Regulated supply from ME6211 |
| GND | `GND` | System ground |
| 5V | *No Connect* | Unused |
| GPIO1 (ADC1_CH0) | `VBAT_SENSE` | Battery voltage monitoring |
| GPIO4 | `SPI_MOSI` | IMU & microSD SPI data out |
| GPIO5 | `SPI_SCK` | IMU & microSD SPI clock |
| GPIO6 | `SPI_MISO` | IMU & microSD SPI data in |
| GPIO7 | `CS_IMU` | IMU chip select |
| GPIO8 | `CS_SD` | microSD chip select |
| GPIO9 | `IMU_INT` | IMU data-ready / interrupt pin |
| GPIO10 | `PWM_M1` | Motor 1 (front-left, CW) |
| GPIO11 | `PWM_M2` | Motor 2 (front-right, CCW) |
| GPIO12 | `PWM_M3` | Motor 3 (rear-right, CW) |
| GPIO13 | `PWM_M4` | Motor 4 (rear-left, CCW) |
| GPIO14 | `BUZZER_CTRL` | Buzzer trigger signal |
| GPIO43 (TX0) | `RC_RX` | Receiver telemetry input (to receiver RX) |
| GPIO44 (RX0) | `RC_TX` | Control signal input (from receiver TX) |

## 3. Electrical Rules Check (ERC) & Netlist Validation

- [ ] Assign `No Connect` (`Q`) to unused pins
- [ ] Run ERC in KiCad and resolve all warnings/errors
- [ ] Validate the updated netlist
