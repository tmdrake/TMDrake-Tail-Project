# TMDrake Tail Project

Open-source purple tech-dergy fursuit tail.

**Long lost tail, several makers later... just gonna open source it.**

![Tail Schematic — Side + Top](tail-schematic.svg)

## Orientation (read this first)

| Side | Name | Description |
|------|------|-------------|
| **Left** in schematic | **Base** | Attaches to the belt / waist. Designed to sit **flush against the body**. |
| **Right** in schematic | **Tip** | Free end. |

- **7 dorsal spikes** — roughly uniform size along the upper ridge (spline)
- **2 side horns** — turquoise, sticking out the sides near the base
- **9 LEDs** total (7 dorsal + 2 side-horn)

The schematic now shows both a **side view** and a **top view** for clearer engineering reference.

## Features
- Sturdy construction (designed to flip inside-out for service)
- 9× WS2812B LEDs (ESP32 + WLED)
- Base kept low-profile so it sits flush at the belt
- Motion-reactive capability via MPU-6050
- Free official Android app through WLED

## Diagrams & Photos

![Diagram](Diagram.jpg)

![Drake Tail V2](Drake%20tail%20V2.png)

![Spikes](Spikes.png)

![Black and purple tail](Black%20and%20purple%20tail%20with%20spikes.jpg)

### Latest assembly finish (2026-07-30)

![Maker finish 1](photo_2026-07-30_09-48-43.jpg)

![Maker finish 2](photo_2026-07-30_18-18-46.jpg)

## Contents
- Spike STLs (`Tailspike-*.stl`)
- Reference photos & fabric links
- `tail-schematic.svg` — dual-view (side + top) LED / spike / base-tip layout
- `DESIGN_NOTES.md` — full orientation, lighting, power, sensor, and construction notes
- `TODO.txt` — remaining pattern & documentation work
- Progress photos: older work in `2024 project/`, new 2026 finish work intended for `2026 project/`

## Status
Almost assembled. Next: LED harness, power, sensors, and WLED/Android control.

MIT License · Drake Dragon
