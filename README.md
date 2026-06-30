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
- **Collects samples** — a 3-DOF robotic arm with a soil scoop and sealed sample container, controlled by inverse kinematics
- **Runs field biology** — automated Biuret protein test (CuSO₄ + NaOH mix) and plant pigment detection, read by an onboard RGB color sensor
- **Measures soil moisture** — capacitive sensor for real-time geology data
- **Can be driven remotely** — full teleop mode with live camera feed over local WiFi

---

## Key specs

| Spec | Value |
|---|---|
| Chassis body | ------ |
| Wheelbase | 1000 mm |
| Wheel diameter | 200 mm |
| Top speed | ~150 mm/s |
| Obstacle clearance | 300 mm (1.5× wheel Ø) |
| Ground clearance | ~248 mm |
| Estimated mass | ~22 kg |
| Suspension | Passive rocker-bogie, 6 wheels |
| Steering | 4 corner wheels (servo) |

---

## Subsystems

| Subsystem | Key components |
|---|---|
| Chassis | Aluminum 2020 extrusion + PLA/PETG 3D-printed joints |
| Mobility | 6× DC motors, BTS7960 drivers, TPU wheels |
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



---

## Printed parts — quick guide



### A couple of things worth knowing before printing

- **The joints set all the angles**, so the aluminum tubes are cut straight at 90°. No mitering needed — that's the whole point of the printed joints.
- **All three wheel mounts share the same 90 mm drop** (socket to wheel center). That's what keeps the three wheels level on the ground — don't change it on just one.

---

## Credits

- Suspension design heavily inspired by [NASA JPL Open Source Rover](https://github.com/nasa-jpl/open-source-rover) — seriously, read their docs, they're great
