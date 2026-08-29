# TODO (Schematic)

Remaining schematic-side tasks for the Trochi mainboard.

## 1. Soft Power Switch (Battery Cutoff)

- [ ] Add SW1 (`K3-1293S-E2`, 3-pin SPDT slide switch): common → R16 → Q6 gate
- [ ] Wire SW1 throws: one → `GND` (switch ON position), other → No Connect
- [ ] Q6 (P-channel MOSFET, e.g. AO3401A): source → `VBAT`, drain → `VBAT_SW` (switched rail feeding regulator & motor drivers), gate → R16
- [ ] R16 (series gate resistor, ~1K) between SW1 and Q6 gate
- [ ] R17 (10K pull-up) between Q6 gate and `VBAT` — keeps Q6 off by default when switch is open

## 2. Electrical Rules Check (ERC) & Netlist Validation

- [ ] Assign `No Connect` (`Q`) to unused pins
- [ ] Run ERC in KiCad and resolve all warnings/errors
- [ ] Validate the updated netlist
