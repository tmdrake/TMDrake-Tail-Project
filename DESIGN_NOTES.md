# TMDrake Tail — Design Notes

## Orientation (critical)

```
BELT / BODY  ─────────────────────────  TIP
     |                                              |
   BASE                                    free end +
 (flush)                                   side horns
```

- **Base** = end that attaches to the belt / waist. Designed to sit **flush against the body**.
- **Tip** = free end. **Two turquoise side horns** sit here (classic dragon-tail layout).
- **Dorsal spikes** = **9** roughly uniform spikes along the upper ridge (spline).
- **Side horns** = 2 turquoise elements sticking out the sides **at the tip**.
- **Total spikes = 11** (9 dorsal + 2 side).

## Dual-view schematic (orthographic)

See `tail-schematic.svg`:

| View | What it shows |
|------|---------------|
| **Side** | Profile: base (left) → tip (right), 9 dorsal spikes on top, side horns at tip |
| **Top**  | Looking down: centerline = dorsal spline, side horns left & right at tip |

- Magenta = dorsal LEDs (9)
- Cyan / turquoise = side-horn LEDs (2) at tip
- **11 LEDs total** (one per spike)

## Lighting layout

- **11× WS2812B** (1 per spike/horn)
- Controller: **ESP32** + **WLED** (free official Android app)
- Power: full white ~60 mA/LED → ~660 mA worst case; purple patterns usually much lower. Size LiPo + 5 V regulator with headroom.

## Sensors / power / construction

- MPU-6050 near base or mid-tail; record axis orientation.
- Battery + ESP32 access preferred at **base** side.
- Flip-inside-out design for service.
- Spike STLs in repo; patterns still needed (see `TODO.txt`).

## Next steps

1. LED string routing (base → tip recommended)
2. Battery / ESP32 pocket at base
3. MPU-6050 mount + axis map
4. WLED 11-LED segment map + reactive effects

MIT License · Drake Dragon
