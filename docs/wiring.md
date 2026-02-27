# Wiring (Arduino ↔ ArduPilot ↔ GPS)

## GPS → Arduino
- GPS TX → Arduino D4 (SoftwareSerial RX)
- GPS RX → Arduino D3 (optional)
- GPS VCC → 5V (or 3.3V if required)
- GPS GND → GND

## Arduino → ArduPilot (TELEM)
- Arduino TX (Serial) → Flight Controller RX (TELEM)
- Arduino RX (Serial) ← Flight Controller TX (TELEM)
- GND ↔ GND

⚠️ Voltage levels: Many FC telemetry ports are 3.3V logic. Use a level shifter if your Arduino is 5V.

## Failsafe Inputs
- Kill switch: Arduino D7 to GND when pressed (uses INPUT_PULLUP)
- Battery: voltage divider output to Arduino A0