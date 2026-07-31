# TMDrake Tail Project

Open-source purple tech-dergy fursuit tail.

**Long lost tail, several makers later... just gonna open source it.**

![Tail Schematic — Side + Top](tail-schematic.svg)

## Orientation

| Side in schematic | Name | Description |
|-------------------|------|-------------|
| **Left** | **Base** | Attaches to belt / waist. Sits **flush against the body**. |
| **Right** | **Tip** | Free end. Two turquoise **side horns** here. |

### Spikes (11 total)
- **9 dorsal spikes** — run down the **back** (upper ridge / spline), roughly uniform size
- **2 side horns** — turquoise, stick out left & right **at the tip** (classic dragon-tail layout)

### LEDs
- **11× WS2812B** (one per spike)
- ESP32 + WLED → free official Android app
- Motion-reactive option via MPU-6050

The schematic is **orthographic** (side + top views) for clear engineering reference.

## Features
- Sturdy, designed to flip inside-out for service
- Base kept low-profile at the belt
- Side horns clustered at the tip
- Full notes in `DESIGN_NOTES.md`

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
- `tail-schematic.svg` — orthographic dual-view (11 spikes / 11 LEDs)
- `DESIGN_NOTES.md` — full orientation, lighting, power, sensor, construction notes
- `TODO.txt` — remaining pattern work
- Progress photos: `2024 project/`, intended `2026 project/` for new finish shots

## Status
Almost assembled. Documentation locked for build hand-off.  
Next: LED harness, power, sensors, WLED / Android control.

MIT License · Drake Dragon
