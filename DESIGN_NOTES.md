# TMDrake Tail — Design Notes

## Orientation (critical)

```
BELT / BODY  ─────────────────────────  TIP
     |                                              |
   BASE                                          SPIKES
 (flush)                                    (angled out)
```

- **Base** = the end that attaches to the belt / waist.  
  It is designed to sit **flush against the body**. Keep this end relatively smooth and low-profile so it doesn’t dig or create a gap under clothing/harness.

- **Tip** = the free end that points away from the wearer.  
  This is where the spikes become larger and more pronounced, and where the tips angle outward.

- **Dorsal spline** = the upper ridge that runs the full length of the tail.  
  All **9 LEDs** live on this spline.

Do **not** reverse base and tip when installing the electronics or sewing the final skin. The flip-inside-out construction assumes this orientation.

## Lighting layout

- **9× WS2812B** addressable LEDs mounted along the dorsal spline.
- Spacing is tighter and visual weight increases toward the tip (matches the physical spike density).
- The two outermost tip-side elements are the more aggressively angled spikes/horns.
- Controller: **ESP32** running **WLED** (gives free official Android app, segments, effects, MQTT, etc.).
- Recommended first presets: purple breathe, fire flicker, reactive ripple.

Power budget (rule of thumb):
- Full white ~60 mA per LED → 9 LEDs ≈ 540 mA worst case.
- Realistic purple patterns usually sit well under 200–300 mA average.
- Size the 5 V regulator and LiPo accordingly and leave headroom.

## Sensors

- **MPU-6050** (or equivalent 6-axis IMU) mounted near the base or mid-tail.  
  Orientation of the sensor axes should be documented once the final mounting orientation is chosen so motion-reactive effects (swish → ripple, hard stop → flash) behave predictably.
- Optional local controls (buttons / capacitive pads) near the base for quick pattern changes without the phone.

## Power & serviceability

- Regulated 5 V from a LiPo pack.
- Battery and ESP32 must remain reachable after the tail is closed — zipper or hidden access panel at the **base** side is preferred so the wearer can service without fully inverting every time.
- The entire structure is designed to **flip inside-out** for deeper maintenance.

## Construction reminders

- Patterns still needed for sides, tops, bottoms, and scale structures (see `TODO.txt`).
- Structure must stay strong enough to invert repeatedly.
- Spike STLs already in the repo (`Tailspike-*.stl` and scaled variants).
- Fabric references present as `.url` files (Fluky Fabrics dragon scales, purple faux fur, hologram tricot, etc.).

## Schematic

See `tail-schematic.svg` (updated 2026-07-30).  
Left = base / belt (flush). Right = tip (spikes angled out). Magenta dots = the 9 LEDs on the dorsal spline.

## Next engineering steps

1. Confirm final LED string routing and data-in direction (base → tip or tip → base).
2. Decide battery + ESP32 pocket location (prefer base side).
3. Mount and orient MPU-6050; record axis mapping.
4. Flash WLED, create a 9-LED segment map, test reactive effects.
5. Document wire gauge, connector type, and any strain-relief points.

MIT License · Drake Dragon
