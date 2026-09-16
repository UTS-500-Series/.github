# 🎛️ UTS Mini Mixing Desk

A small analogue mixing desk built from **500-series modules**, designed as a project at the
University of Technology Sydney (UTS).

📖 **Documentation: [uts-500-series.github.io](https://uts-500-series.github.io/)** — how every
module works, section by section, with interactive schematics for the compressor.

## 📖 About the project

The desk is a rack of three modules, each a card in the API 500-series format. Every module
shares the same constraints, which is what lets them sit side by side in one rack:

| Constraint | Value |
| :--- | :--- |
| Panel | 1.5 × 5.25 in — 38.10 × 133.35 mm |
| Connector | 15-pin, 0.156 in card edge |
| Supply | ±16 V, 130 mA per rail |
| Phantom | +48 V on pin 15 |
| Audio | Balanced in and out |

## 📂 Repositories

| Repository | Module | Status | Contents |
| :--- | :--- | :--- | :--- |
| [**Compressor**](https://github.com/UTS-500-Series/Compressor) | Compressor | Designed — not yet built | KiCad 9 schematic across seven sheets; `tools/` holding the netlist as data (`design.py`) and the scripts that generate and verify the schematic against it; `panel/` generating the faceplate mockup, 1:1 drawing and DXF |
| [**Equaliser**](https://github.com/UTS-500-Series/Equaliser) | Equaliser | In progress | KiCad schematics for a state-variable parametric band (`LBP/`) and a Sallen-Key low-pass (`LPF/`); an LTspice simulation of one band (`LBPF/BandA`); a BOM template |
| [**Pre-Amp**](https://github.com/UTS-500-Series/Pre-Amp) | Preamp | Getting started | Empty for now. The preamp is based on ESP Project 66 with Project 96 phantom power — see the documentation |
| [**UTS-500-Series.github.io**](https://github.com/UTS-500-Series/UTS-500-Series.github.io) | — | Live | The documentation site: a Python generator in `build/`, the published pages in `site/` |

### 🎚️ Compressor

A feedback compressor built round a discrete current-steering gain cell, using NE5532 op amps
and BC549 transistors. It has balanced I/O, a sidechain with a key input, stereo link, and
seven-LED gain-reduction and output-level meters.
[Documentation →](https://uts-500-series.github.io/compressor/)

### 🎛️ Equaliser

Filter sections built round the OPA1641: state-variable parametric bands with frequency, width
and gain controls, plus a Sallen-Key low-pass. One band has been simulated; component values
are still being carried onto the schematics.
[Documentation →](https://uts-500-series.github.io/equaliser/)

### 🎤 Preamp

A very low-noise balanced microphone preamp using discrete Sziklai transistor pairs and an
op-amp difference stage, with 48 V phantom power taken from the rack. The circuit is
[ESP Project 66](https://sound-au.com/project66.htm) by Rod Elliott, with phantom distribution
from [Project 96](https://sound-au.com/project96.htm).
[Documentation →](https://uts-500-series.github.io/preamp/)

## 🛠️ Tools

- **Schematics & PCB:** KiCad 9
- **Simulation:** LTspice
- **Design automation:** Python — netlist generation, schematic routing and verification, faceplate generation
- **Documentation:** a static site generated in Python, published with GitHub Pages; interactive schematics use cytoscape.js

## 🚀 Getting started

Clone the module you want to work on and read its `README.md`:

```bash
git clone https://github.com/UTS-500-Series/Compressor.git
```

In the compressor, check the schematic still matches its netlist after any edit:

```bash
python3 tools/verify_netlist.py
```

<!--
## 👥 Team

| Name | Focus | GitHub |
| :--- | :--- | :--- |
| | | |
-->

## 📜 Academic integrity & licensing

This project is coursework at the **University of Technology Sydney**. UTS academic integrity
policies apply to all enrolled students working with this material.

No licence has been chosen for these repositories yet, so all rights are reserved by default.

The preamp circuit is **not our design**: it is ESP Project 66 by Rod Elliott, whose terms
permit construction for personal use but not commercial manufacture.

---
*Developed with 🎧 in Sydney, Australia.*
