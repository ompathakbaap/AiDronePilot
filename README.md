# ArduPilot ↔ Arduino Companion: GPS Navigation + Failsafe

This repo demonstrates integrating an Arduino as a companion controller for an ArduPilot-based drone.

## What it does
- Reads GPS (NMEA) on Arduino
- Monitors failsafe conditions:
  - Kill switch input
  - Low battery threshold
- Sends MAVLink command to ArduPilot to trigger RTL (Return-To-Launch) when failsafe occurs

## Why this matters
ArduPilot handles stabilization and flight control. The Arduino acts as an external watchdog:
- Adds custom safety logic
- Can trigger autonomous behaviors through MAVLink

## Files
- `arduino/companion_gps_failsafe.ino` — GPS + failsafe logic + MAVLink command
- `docs/wiring.md` — wiring overview