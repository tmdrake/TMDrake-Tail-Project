# TMDrake Tail — Design Notes

Final reference for orientation, spikes, lighting, and build hand-off.  
Updated 2026-07-30.

---

## 1. Orientation (critical)

```
BELT / BODY  ─────────────────────────  TIP
     |                                              |
   BASE                                    free end +
 (flush)                                   side horns
```

| End | Name | Description |
|-----|------|-------------|
| **Left** in schematic | **Base** | Attaches to the belt / waist. Designed to sit **flush against the body**. Keep low-profile. |
| **Right** in schematic | **Tip** | Free end pointing away from the wearer. Side horns live here. |

Do **not** reverse base and tip when wiring LEDs or sewing the final skin. The flip-inside-out construction assumes this orientation.

---

## 2. Spikes (11 total)

### Dorsal spikes (9)
- Run down the **back** of the tail along the upper ridge (the **dorsal spline**).
- Roughly **uniform** size along the length.
- These are the spikes you see in a classic side silhouette of a dragon tail.

### Side horns (2)
- **Turquoise** in the schematic.
- Stick out **left and right** at the **tip** (not on the dorsal line).
- Classic dragon-tail layout: the extra points flare at the free end.

**Total = 11 spikes** (9 dorsal + 2 side horns).

---

## 3. Orthographic schematic

File: `tail-schematic.svg`

| View | Purpose |
|------|--------|
| **Side** | Elevation: base → tip profile, body thickness, dorsal spike height, side-horn angle |
| **Top**  | Plan: centerline = dorsal spline, left/right side-horn placement at tip |

These are **orthographic** projections (no perspective). Use them for placement and routing, not for artistic mood.

Legend in the SVG:
- Magenta dots = dorsal LEDs
- Cyan / turquoise dots + shapes = side-horn LEDs at tip

---

## 4. Lighting

- **11× WS2812B** addressable LEDs (one per spike/horn).
- Controller: **ESP32** running **WLED**.
- Free official Android app for patterns, brightness, segments, effects.
- Recommended first presets: purple breathe, fire flicker, reactive ripple.

**Power budget (rule of thumb)**  
- Full white ~60 mA per LED → 11 LEDs ≈ 660 mA worst case.  
- Realistic purple patterns usually sit well under that.  
- Size the 5 V regulator and LiPo with headroom. Keep battery accessible via zipper at the **base** side.

**Suggested data direction:** base → tip (first LED near belt, last LEDs on the tip horns).

---

## 5. Sensors

- **MPU-6050** (or similar 6-axis IMU) for motion-reactive modes (swish → ripple, impact → flash).
- Mount near base or mid-tail. **Record the final axis orientation** so effects behave predictably.
- Optional: buttons or capacitive pads near the base for local control without the phone.

---

## 6. Construction & service

- Structure is designed to **flip inside-out** for maintenance.
- Battery + ESP32 pocket preferred at the **base** (belt end) so the wearer can service without full inversion every time.
- Spike STLs already in repo (`Tailspike-*.stl` and scaled variants).
- Patterns for sides, tops, bottoms, and scale structures still needed (see `TODO.txt`).
- Fabric references present as `.url` files (Fluky Fabrics dragon scales, purple faux fur, hologram tricot, etc.).

---

## 7. Next engineering steps (for build agent)

1. Confirm LED string routing and data-in direction (base → tip recommended).
2. Place battery + ESP32 pocket at base; add zipper or access panel.
3. Mount and orient MPU-6050; document axis mapping.
4. Flash WLED, create an 11-LED segment map, test reactive effects.
5. Note wire gauge, connector type, and strain-relief points.

---

MIT License · Drake Dragon
