# Release Notes

## v1.0 — Initial Hardware Release

First complete schematic-to-manufacturing cycle for the Trochi mainboard.

### Power
- LiPo battery input with soft power switch (P-MOSFET, driven by SPDT slide switch)
- 3.3V LDO regulation with split input/output filter capacitance

### Sensors & Storage
- ICM-42688-P 6-axis IMU
- microSD card storage (TF-021B-H265, compact push-pull socket)

### Motors & Indicators
- 4x coreless motor drivers (N-MOSFET, PWM-controlled)
- Status LED (3.3V indicator)
- Active buzzer circuit

### Connectivity
- ESP32-S3 SuperMini shield header (1x9 male/female)
- WiFi/ESP-NOW control via ESP-Drone firmware (no dedicated RC receiver)

### PCB
- 2-layer routing (bottom and top) with ground pour
- Rounded board outline, silkscreen artwork and logos
- DRC clean (0 errors, 9 cosmetic warnings)
- Gerber and drill files generated

### Removed During Development
- ELRS receiver connector (superseded by WiFi/ESP-NOW control)
