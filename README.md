# ROVER "Target Fidelity"

A low-budget, 6-wheel autonomous rover that drives itself through rough terrain, collects soil and plant samples, and runs onboard biology and geology tests — all built from 3D-printed parts, off-the-shelf motors, and open-source software. Or so I hope.

---

> *[GIF coming soon — first field test]*

---

## The demo

**[coming soon]**

---

## What it does

- **Drives itself** — autonomous navigation with SLAM mapping and AR marker detection
- **Handles rough terrain** — rocker-bogie passive suspension (inspired by JPL's open-source rover) keeps all 6 wheels on the ground on dirt, gravel, and grass
- **Real differential** — a balancín + bieletas linkage (like the actual JPL rover) keeps the chassis level when the two sides climb at different heights
- **Collects samples** — a 3-DOF robotic arm with a soil scoop and sealed sample container, controlled by inverse kinematics
- **Runs field biology** — automated Biuret protein test (CuSO₄ + NaOH mix) and plant pigment detection, read by an onboard RGB color sensor
- **Measures soil moisture** — capacitive sensor for real-time geology data
- **Can be driven remotely** — full teleop mode with live camera feed over local WiFi

---

## Key specs

| Spec | Value |
|---|---|
| Chassis body | 900 × 600 mm |
| Wheelbase | 1000 mm |
| Wheel diameter | 200 mm |
| Top speed | ~150 mm/s |
| Obstacle clearance | 300 mm (1.5× wheel Ø) |
| Ground clearance | ~248 mm |
| Estimated mass | ~30 kg |
| Suspension | Passive rocker-bogie, 6 wheels |
| Differential | Real (balancín + bieletas, chassis-leveling) |
| Steering | 4 corner wheels (servo) |

---

## Subsystems

| Subsystem | Key components |
|---|---|
| Chassis | Aluminum 2020 extrusion + PLA/PETG 3D-printed joints |
| Mobility | 6× JGB37 DC motors, BTS7960 drivers, TPU wheels |
| Differential | Balancín + 2 bieletas with ball-joint ends |
| Steering | 4× MG996R servos + PCA9685 |
| Brain | Raspberry Pi 4 + Arduino R4 |
| Vision | WIP |
| Navigation | WIP |
| Sampling arm | WIP |
| Lab | TCS34725 color sensor, peristaltic pump, syringe dispenser |
| Geology | Capacitive soil moisture sensor |

---

## Bill of Materials (mobility system)

Just the drive/suspension parts for now — the rest is still WIP.

### Hardware

| # | Part | Qty | Notes |
|---|---|---|---|
| 1 | JGB37 12V 50RPM gearmotor (40 kg·cm) | 6 | drive motors — confirm encoder version for SLAM |
| 2 | BTS7960 43A motor driver | 2 | one per side, 3 motors paralleled each |
| 3 | MG996R servo | 4 | corner-wheel steering |
| 4 | PCA9685 16-ch PWM driver | 1 | drives the steering servos over I2C |
| 5 | Aluminum round tube Ø25×2 mm | ~1.6 m | rocker arms |
| 6 | Aluminum round tube Ø20×2 mm | ~0.9 m | bogie arms |
| 7 | Steel rod Ø12 × 700 mm | 1 | differential axle (600 in chassis + 50 each boss) |
| 8 | Steel pin Ø12 × 40 mm | 11 | pivots (2 rocker + 2 bogie + 6 wheel + 1 spare) |
| 9 | Aluminum 2020 extrusion | ~3 m | chassis frame |
| 10 | T-nuts + corner brackets (2020) | ~30 | frame + panel assembly |
| 11 | Rod-end ball joints (M5) | 4 | bieleta ends — both ends of each rod |
| 12 | Threaded rod M5 (bieletas) | ~0.5 m | cut to ~253 mm each |
| 13 | Bolt M5×20 + nylock | ~40 | tube-to-joint, clamps |
| 14 | Bolt M4×16 | ~16 | bearing blocks to chassis |
| 15 | Bolt M3×20 + nylock | ~36 | rim halves |
| 16 | LiPo battery 12V 8–10 Ah | 1 | handles ~26 A climbing peaks |
| 17 | Raspberry Pi 4 (4 GB) | 1 | high-level brain |
| 18 | Arduino R4 | 1 | motor/servo/encoder low-level control |

### Filament

| Material | Approx. use | For |
|---|---|---|
| PETG | ~600 g | joints, wheel mounts, rims, bearing blocks, balancín, clamps |
| TPU 95A | ~250 g | tires |

---

## Printed parts — quick guide

### A couple of things worth knowing before printing

- **The joints set all the angles**, so the aluminum tubes are cut straight at 90°. No mitering needed — that's the whole point of the printed joints.
- **All three wheel mounts share the same 90 mm drop** (socket to wheel center). That's what keeps the three wheels level on the ground — don't change it on just one.
- **The differential bieletas need ball joints on both ends** — a rigid connection binds the linkage. The 1:1 ratio (balancín arm = clamp offset = 180 mm) is what keeps the leveling symmetric.
- **Joint walls are 5 mm** — don't go thinner or the M5 bolts pull out of the PETG under load.

---

## Credits

- Suspension design heavily inspired by [NASA JPL Open Source Rover](https://github.com/nasa-jpl/open-source-rover) — seriously, read their docs, they're great