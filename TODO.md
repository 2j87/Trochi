# TODO

Remaining schematic-side tasks for the Trochi mainboard.

## 1. External Receiver Port (ELRS / FlySky / SBUS)

- [ ] Add connector: `Connector_Generic:Conn_01x04` (J7)
- [ ] Pin 1 → `+3.3V` (supply)
- [ ] Pin 2 → `GND`
- [ ] Pin 3 → net label `RC_RX` (to ESP32 TX pin / telemetry)
- [ ] Pin 4 → net label `RC_TX` (to ESP32 RX pin / control signal)

## 2. Status Indicators

### Power LED (3.3V indicator)

- [ ] D5 (0603 LED): anode → `+3.3V`
- [ ] Cathode → R13 (1K) → `GND`

### Active Buzzer Circuit

- [ ] BZ1 (2-pin header/pad): (+) → `VBAT`, (-) → Q5 drain
- [ ] D6 (Schottky SS14 or 1N4148) as flyback diode across BZ1 (cathode → `VBAT`, anode → Q5 drain)
- [ ] Q5 (AO3400A / 2N7002): source → `GND`, drain → BZ1 (-)
- [ ] R14 (1K series gate resistor) → `BUZZER_CTRL`
- [ ] R15 (10K pull-down) between gate and `GND`

## 3. ESP32-S3 SuperMini Header & Pin Assignment

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

## 4. Electrical Rules Check (ERC) & Netlist Validation

- [ ] Assign `No Connect` (`Q`) to unused pins
- [ ] Run ERC in KiCad and resolve all warnings/errors
- [ ] Validate the updated netlist
