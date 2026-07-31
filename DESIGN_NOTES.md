# TMDrake Tail — Design Notes

## Orientation (critical)

```
BELT / BODY  ─────────────────────────  TIP
     |                                              |
   BASE                                          free end
 (flush)
```

- **Base** = end that attaches to the belt / waist.  
  Designed to sit **flush against the body**. Keep this end low-profile.

- **Tip** = free end pointing away from the wearer.

- **Dorsal spikes** = 7 roughly **uniform** spikes running down the upper ridge (spline).

- **Side horns** = 2 turquoise elements sticking out the **sides** near the base.

Do not reverse base and tip when installing electronics or sewing the final skin.

## Dual-view schematic

See `tail-schematic.svg` for both:

| View | What it shows |
|------|---------------|
| **Side** | Profile: base (left) → tip (right), dorsal spikes on top, side horns near base |
| **Top**  | Looking down: centerline = dorsal spline, side horns left & right near base |

- Magenta dots = dorsal LEDs (7)
- Cyan / turquoise dots + shapes = side-horn LEDs (2)

## Lighting layout

- **9× WS2812B** total:
  - 7 LEDs on the dorsal spikes (magenta)
  - 2 LEDs on the side horns (turquoise)
- Controller: **ESP32** running **WLED** (free official Android app).
- Recommended first presets: purple breathe, fire flicker, reactive ripple.

Power budget (rule of thumb):
- Full white ~60 mA per LED → 9 LEDs ≈ 540 mA worst case.
- Realistic purple patterns usually sit under 200–300 mA average.
- Size the 5 V regulator and LiPo with headroom.

## Sensors

- **MPU-6050** (or equivalent 6-axis IMU) mounted near the base or mid-tail.
- Record the final sensor axis orientation so motion-reactive effects behave predictably.
- Optional local controls (buttons / capacitive pads) near the base.

## Power & serviceability

- Regulated 5 V from a LiPo pack.
- Battery and ESP32 should remain reachable after the tail is closed — zipper or access panel at the **base** side preferred.
- Structure is designed to **flip inside-out** for deeper maintenance.

## Construction reminders

- Patterns still needed for sides, tops, bottoms, and scale structures (see `TODO.txt`).
- Structure must stay strong enough to invert repeatedly.
- Spike STLs already in the repo (`Tailspike-*.stl` and scaled variants).
- Fabric references present as `.url` files.

## Next engineering steps

1. Confirm final LED string routing and data-in direction (base → tip recommended).
2. Decide battery + ESP32 pocket location (prefer base side).
3. Mount and orient MPU-6050; record axis mapping.
4. Flash WLED, create a 9-LED segment map, test reactive effects.
5. Document wire gauge, connector type, and strain-relief points.

MIT License · Drake Dragon
