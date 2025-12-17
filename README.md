# ⚡🔌🔋 UAV Power Distribution & Regulation Board

## Overview

This repository documents an **updated power stage for an unmanned aerial vehicle (UAV)**, developed as a **standalone PCB** to improve system modularity, robustness, and power integrity.

Originally, the power management circuitry was integrated on the same PCB as the **MCU, IMU, and control electronics**.  
In this revision, the power stage was **fully separated into a dedicated board**, enabling a clear functional separation between:

- **Power distribution and regulation**
- **Control, sensing, and navigation electronics**

This modular architecture simplifies debugging, testing, maintenance, and future system upgrades, while improving isolation between high-current and low-power domains.

## 📂 Contents
- `/Hardware` →  Schematic, PCB, Gerbers.


## 🔗 Project Context

This power distribution and regulation board is part of the ongoing hardware updates for the **DIY UAV project**.

The main project repository documents the overall UAV system, including mechanical design, control architecture, and system integration:

- **DIY UAV – Main Project Repository**  
  [DIY UAV](https://github.com/CrissCCL/DIY_UAV)

This repository focuses exclusively on the **power stage modularization**, extracted from the original integrated PCB to improve system scalability, maintainability, and electrical robustness.

## 🧩 System Architecture

The UAV electronics are now divided into two main subsystems:

1. **Power Stage (this repository)**
2. **Control & Sensing Stage (MCU + IMU)**

The power board is responsible for managing the **battery input**, distributing high-current power to the ESCs, and providing regulated power for low-voltage electronics.


## 🔗 Power Flow Architecture

The power distribution follows a centralized architecture in which the battery input is first managed by a high-side power switch, and then distributed to both high-current and low-voltage domains.

```text
Battery
  │
  └── BTS50005-1LUA
        ├──► ESC Power Distribution
        └──► LM2596 Buck Regulator ──► MCU / IMU / Control Electronics
```

## 🖼️ PCB Render Visualization

<table>
  <tr>
    <td align="center">
      <img alt="stage power dron_v1_front" src="https://github.com/user-attachments/assets/54d63556-4770-4720-82ef-f94c9d20400e" width="550"><br>
      <sub> Power Stage PCB – Top View </sub>
    </td>
    <td align="center">
        <img alt="stage power dron_v1_back" src="https://github.com/user-attachments/assets/6728142b-c3ae-4e01-b3f8-c969f5ee0fdc" width="550"><br>
      <sub>Power Stage PCB – Bottom View </sub>
    </td>
  </tr>
</table>

### Integrated Power Architecture Diagram

<p align="center">
<img width="700" alt="stage power dron_v1" src="https://github.com/user-attachments/assets/bec7881d-a832-427a-b596-c14706bd7e3a" />
</p>

## 📜 License
MIT License
