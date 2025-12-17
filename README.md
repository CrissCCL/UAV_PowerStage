# ⚡🔌 🔋 UAV Power Distribution & Regulation Board

## Overview

This repository documents an **updated power stage for an unmanned aerial vehicle (UAV)**, developed as a **standalone PCB** to improve system modularity and robustness.

Originally, the power management circuitry was integrated on the same PCB as the **MCU, IMU, and control electronics**.  
In this revision, the power stage was **fully separated into a dedicated board**, allowing a clear functional split between:

- **Power distribution and regulation**
- **Control, sensing, and navigation electronics**

This modular approach simplifies debugging, testing, maintenance, and future system upgrades.


## 🧩 System Architecture

The UAV electronics are now divided into two main subsystems:

1. **Power Stage (this repository)**
2. **Control & Sensing Stage (MCU + IMU)**

The power board is responsible for managing the **battery input**, distributing high-current power to the ESCs, and providing regulated power for low-voltage electronics.


## ⚡ Power Stage Description

The power stage integrates the following main components on a **single dedicated PCB**:

### 🔋 Battery Input & High-Current Distribution

- **Component:** BTS50005-1LUA  
- **Function:**  
  - High-side power switch
  - Current handling and protection
  - Controlled power distribution to multiple ESCs

The BTS50005-1LUA is used to safely manage the energy delivered from the UAV battery to the **electronic speed controllers (ESCs)**, providing robustness against overcurrent and fault conditions.


### 🔌 Low-Voltage Regulation

- **Component:** LM2596 (buck regulator)
- **Function:**  
  - Step-down conversion from battery voltage
  - Stable supply for:
    - MCU
    - IMU
    - Auxiliary low-power electronics

By integrating the LM2596 on the same PCB, the board provides a **clean and centralized power source** for the control subsystem.


## 🔗 Power Flow Summary

```text
Battery
  │
  ├── BTS50005-1LUA ──► ESC Power Distribution
  │
  └── LM2596 ─────────► MCU / IMU / Control Electronics
```
