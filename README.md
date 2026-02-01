# ⚡🔌🔋 UAV Power Distribution & Regulation Board

![Hardware](https://img.shields.io/badge/Hardware-Power%20Stage-blue)
![PCB](https://img.shields.io/badge/PCB-KiCad-lightgrey)
![Power](https://img.shields.io/badge/Power-Distribution%20%26%20Regulation-orange)
![Embedded](https://img.shields.io/badge/Embedded-UAV%20Platform-lightgrey)
![License](https://img.shields.io/badge/License-See%20repo-lightgrey)


## Overview

This repository documents an **updated power stage for an unmanned aerial vehicle (UAV)**, developed as a **standalone PCB** to improve system modularity, robustness, and power integrity.

Originally, the power management circuitry was integrated on the same PCB as the **MCU, IMU, and control electronics**.  
In this revision, the power stage was **fully separated into a dedicated board**, enabling a clear functional separation between:

- **Power distribution and regulation**
- **Control, sensing, and navigation electronics**

This modular architecture simplifies debugging, testing, maintenance, and future system upgrades, while improving isolation between high-current and low-power domains.

## 📂 Contents
- `/Hardware` →  Schematic, Gerbers.

## 🌐 YouTube

📺 [Upgrade Power Stage](https://youtube.com/shorts/vSKApaUKDLE?feature=share)


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

## ⚡ Physical Prototype

The following image shows the complete setup of the **prototype version**:

<table>
  <tr>
    <td align="center">
      <img alt="stage power dron_v1_front" src="https://github.com/user-attachments/assets/aa7f3e3f-6424-4d1b-8d71-56b7c1358583" width="400"><br>
      <sub> Power Stage PCB V1 – Top View </sub>
    </td>
    <td align="center">
        <img alt="stage power dron_v1_back" src="https://github.com/user-attachments/assets/ee7d4e42-d4eb-4bcf-9f91-032cfe8f443f" width="400"><br>
      <sub>Power Stage PCB V1 – Bottom View </sub>
    </td>
  </tr>
</table>

## ⚠️ Disclaimer

This project is intended **for educational and experimental purposes only**.

The power distribution and regulation board is **not flight-certified** and has not been validated under aviation or safety-critical standards.

Users are responsible for ensuring safe operation, proper electrical protection, and compliance with applicable regulations when working with high-current systems.


## 🤝 Support projects
 Support me on Patreon [https://www.patreon.com/c/CrissCCL](https://www.patreon.com/c/CrissCCL)

## 📜 License
MIT License
