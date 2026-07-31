# TMDrake Tail — Design Notes

## Overview
Sturdy purple tech-dergy tail. 7 dorsal spikes + 2 side horns. Designed to flip inside-out for maintenance.

## Lighting (current plan)
- **9× WS2812B** addressable LEDs (1 per spike/horn)
- Controller: **ESP32** running **WLED**
- Free official Android app for patterns, brightness, segments, effects
- Purple breathing / fire flicker presets work great

## Sensors
- **MPU-6050** (or similar IMU) for motion-reactive modes (swish → ripple, impact → flash)
- Optional: simple buttons or capacitive pads near base for local control

## Power
Regulated 5 V LiPo pack sized for the LED count + headroom. Keep battery accessible via zipper.

## Construction notes (from existing TODO)
- Patterns still needed for sides, tops, bottoms, scale structures
- Must remain strong enough to invert
- Spike STLs already in repo (`Tailspike-*.stl`)
- Fabric references: Fluky Fabrics dragon scales, purple faux fur, hologram tricot

## Next steps
1. Finalize patterns & document dimensions
2. Wire LEDs + ESP32 inside before final close
3. Test WLED + MPU6050 reactive effects
4. Add battery compartment + zipper access

MIT License · 2025 Drake Dragon
