# MANDOR — 3D Mechanical Designs 🛠️

**M**achine **An**alytics & **N**etwork **D**iagnostic **O**perations **R**outer

![Status](https://img.shields.io/badge/status-prototype-orange)
![CAD](https://img.shields.io/badge/CAD-SolidWorks-red)

This repository contains SolidWorks source files for the mechanical components of the **MANDOR predictive maintenance conveyor system** — an IoT and Edge AI-based closed-loop industrial control rig: panel walls, the sensor-mounting brackets, and a few structural parts from the conveyor rig.

> ⚠️ **Note from the author:** only a few of these designs made it into the final built prototype — some parts here are earlier iterations or explorations that were superseded. See the [file table](#-repository-contents) below for what's current.

> 🔗 Looking for the firmware / Edge AI code instead of the mechanical design? Link the main MANDOR repository here once it's public.

---

## Table of Contents

- [About the Prototype](#-about-the-prototype)
- [Repository Contents](#-repository-contents)
- [Design Gallery](#️-design-gallery)
- [Opening These Files](#-opening-these-files)
- [Recommended Manufacturing](#️-recommended-manufacturing)
- [Disclaimer](#️-disclaimer)
- [Authors](#-authors)
- [Contributing](#-contributing)

---

## 📖 About the Prototype

MANDOR is an IoT and Edge AI-based predictive maintenance system designed for closed-loop industrial control. The parts in this repository belong to the physical testing rig: a miniature conveyor belt, a centralized control enclosure (the "panel box"), and mounting mechanisms for non-contact telemetry sensors.

The mechanical design is aimed at:

- **Split Power/Logic Placement** — an enclosure that keeps the ESP32 microcontroller, motor driver, and power regulators safely housed.
- **Interference-Free Sensor Mounting** — mounts that hold the vibration and infrared temperature sensors on the DC motor gearbox without touching moving parts.
- **Modular Assembly** — the panel box is built from separate wall parts ("Dinding …") rather than one solid enclosure, so individual faces can be reprinted or redesigned on their own.

---

## 📂 Repository Contents

All files currently live flat in the repository root — there are no subfolders yet. Everything is native **SolidWorks** (`.SLDPRT` = part, `.SLDASM` = assembly).

| File                                       | Type     | What it is                                                                  |
| ------------------------------------------ | -------- | --------------------------------------------------------------------------- |
| `Assem24.SLDASM`                           | Assembly | Main/top-level assembly                                                     |
| `Puzzle Kotak Panel.SLDASM`                | Assembly | Panel box assembly — combines the wall parts below                          |
| `Dinding atas fix.SLDPRT`                  | Part     | Panel box — top wall (finalized version)                                    |
| `Dinding Bawah.SLDPRT`                     | Part     | Panel box — bottom wall                                                     |
| `Dinding belakang.SLDPRT`                  | Part     | Panel box — back wall                                                       |
| `Dinding Kanan.SLDPRT`                     | Part     | Panel box — right wall                                                      |
| `Dinding Kiri.SLDPRT`                      | Part     | Panel box — left wall                                                       |
| `Penutup_fix.SLDPRT`                       | Part     | Enclosure cover (finalized version)                                         |
| `Panel Komponen.SLDPRT`                    | Part     | Component mounting panel (internal)                                         |
| `dudukan sensor suhu sama motornya.SLDASM` | Assembly | Temperature sensor mount + motor sub-assembly                               |
| `Dudukan sensor suhu MLX.SLDPRT`           | Part     | MLX90614 infrared sensor mount                                              |
| `bracket optocoupler.SLDPRT`               | Part     | Optocoupler sensor bracket                                                  |
| `Pinggiran Roller.SLDPRT`                  | Part     | Roller edge / rim piece                                                     |
| `parametric encoder wheel.SLDPRT`          | Part     | Parametric encoder wheel (dimensions driven by SolidWorks equations/config) |

> As you clean up which designs are final, consider moving them into `Assemblies/` and `Parts/` folders and updating this table — right now everything is intentionally listed flat to match what's actually pushed.

---

## 🖼️ Design Gallery

> No images are pushed to this repository yet. Once you add them, create an `images/` folder in the repo root, upload your renders there, and fill in the sections below — replace the alt text and captions with what each image actually shows.

### 1. Full Isometric View

<p align="center">
  <img src="Asset Image/Propto Overview.png" alt="Full isometric view of the MANDOR conveyor assembly" width="70%">
</p>

_Complete mechanical assembly of the miniature conveyor machine, showing the control panel mounted on the side of the conveyor frame._

### 2. Control Panel Enclosure (Edge AI & IoT Hub)

<p align="center">
  <img src="Asset Image/images2(PanelBox).png" alt="Control panel enclosure housing the ESP32 and motor driver" width="70%">
</p>

_The main enclosure, assembled from `Puzzle Kotak Panel.SLDASM` and its wall parts. Houses the ESP32 microcontroller and motor driver, with an external mount for the OLED interface._

### 3. Sensor Mounting on DC Motor Gearbox

<p align="center">
  <img src="Asset Image/BracketforSensors.png" alt="Vibration and infrared sensor mounts on the DC motor gearbox" width="70%">
</p>

_Close-up of `dudukan sensor suhu sama motornya.SLDASM` — the vibration sensor and the MLX90614 infrared sensor mounted directly on the motor casing for accurate, non-contact telemetry._

<details>
<summary><b>Template for adding more gallery images</b></summary>

```markdown
### N. Short Title

<p align="center">
  <img src="images/your-file-name.png" alt="Descriptive alt text for accessibility" width="70%">
</p>

_One or two sentences describing what this view shows and which file it comes from._
```

</details>

---

## 🔧 Opening These Files

These are native SolidWorks files, so the most reliable way to open them is SolidWorks itself. If you don't have a license:

1. **eDrawings** (free) — Dassault Systèmes' free viewer opens `.SLDPRT`/`.SLDASM` for viewing, measuring, and basic section views, though not editing. [Download eDrawings](https://www.edrawingsviewer.com/).
2. **SolidWorks assemblies expect their part files in the same folder** — when opening `Assem24.SLDASM`, `Puzzle Kotak Panel.SLDASM`, or `dudukan sensor suhu sama motornya.SLDASM`, clone or download the whole repository rather than a single file, or SolidWorks won't be able to resolve the linked parts.
3. **3D printing:** none of these parts have an exported `.STL` in this repo yet. Export one from SolidWorks (`File → Save As → STL`) before sending a part to a slicer.

---

## ⚙️ Recommended Manufacturing

| Component              | Method                      | Suggested Material                                                                   |
| ---------------------- | --------------------------- | ------------------------------------------------------------------------------------ |
| Panel walls & brackets | 3D Printed (FDM)            | PLA / PETG for general use; ABS or ASA for parts near the motor that see higher heat |
| Frame                  | Standard aluminum extrusion | 2020 V-slot, sized to the assembly dimensions                                        |

**Print settings (starting point):** 0.2 mm layer height, ≥20% infill for brackets, 100% infill or added wall loops for load-bearing mounting points near the motor.

---

## ⚠️ Disclaimer

Please note that I am not a professional mechanical engineer or a highly experienced 3D designer. These models were created as a functional prototype to bring the MANDOR project to life. As such, the designs may have room for improvement regarding structural optimization, precise tolerances, or standard mechanical practices.

**Only a few of the designs in this repository were used in the final built prototype** — several parts here are earlier iterations kept for reference rather than the as-built version.

Constructive feedback, suggestions, or contributions to improve the designs are highly appreciated!

---

## 👥 Authors

**Team RESTU MAMAH PAPAH** — Politeknik Manufaktur Bandung

- Bintang Shobri Al Chakim
- Ilham Nur Fiqri
- Muhammad Daffi Izzuddin

---

## 🤝 Contributing

Suggestions and pull requests are welcome — especially around structural optimization, tolerancing, or DFM (design-for-manufacturing) improvements. Please open an issue first to discuss what you'd like to change.
