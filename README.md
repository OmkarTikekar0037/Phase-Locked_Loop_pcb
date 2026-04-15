# Discrete Phase-Locked Loop (PLL) on PCB

This project implements a **fully discrete Phase-Locked Loop (PLL)** using standard logic ICs, analog components, and a voltage-controlled oscillator on a custom PCB. The goal is to bridge theoretical understanding of PLLs with practical hardware realization by designing, building, and analyzing a complete feedback synchronization system.

---

## 🔷 Overview

The PLL is designed to:

* Lock onto an external reference signal (100 Hz – 10 kHz range)
* Perform **frequency multiplication** (×2, ×4, ×8 configurable)
* Demonstrate **lock acquisition (capture)** and **tracking (lock range)** behavior
* Provide observable internal signals for analysis (UP, DOWN, Vctrl, VCO output)

This implementation emphasizes **control system behavior**, **nonlinear dynamics**, and **real-world circuit constraints**.

---

## 🔷 System Architecture

The PLL is composed of the following functional blocks:

1. **Phase Frequency Detector (PFD)**

   * Built using dual D flip-flops and NAND logic
   * Generates UP/DOWN signals based on phase and frequency difference

2. **Charge Pump**

   * Converts digital UP/DOWN pulses into current pulses
   * Controls charging/discharging of the loop filter

3. **Loop Filter (RC Network)**

   * Integrates charge pump output into a smooth control voltage (Vctrl)
   * Defines loop dynamics (bandwidth, damping, stability)

4. **Voltage Controlled Oscillator (VCO)**

   * Implemented using a 555 timer in voltage-controlled mode
   * Output frequency varies with Vctrl

5. **Frequency Divider**

   * Digital counter used to scale down VCO output
   * Enables frequency multiplication in closed loop

---

## 🔷 Key Design Features

* **Second-order PLL design** with tunable damping factor (ζ ≈ 0.7)
* Adjustable loop parameters (R, C, charge pump current)
* Modular block-based design for easy debugging and testing
* Dedicated test points for internal signal observation
* Separation of analog and digital sections for noise reduction

---

## 🔷 Learning Objectives

This project demonstrates:

* Practical implementation of **feedback control systems**

* Relationship between **phase, frequency, and time-domain behavior**

* Design trade-offs between:

  * Stability vs speed
  * Capture range vs noise
  * Loop gain vs oscillation

* Real-world non-idealities:

  * Charge pump mismatch
  * Loop filter noise sensitivity
  * VCO nonlinearity

---

## 🔷 Observations & Experiments

The setup allows direct observation of:

* Lock acquisition process (capture range behavior)
* Stable locked state (minimal phase error)
* Effect of loop filter parameters on system response
* Impact of VCO gain and charge pump current on stability

---

## 🔷 Applications

While implemented as a low-frequency prototype, the same principles apply to:

* Microcontroller clock generation
* RF frequency synthesizers
* Motor synchronization systems
* Communication systems (clock/data recovery)

---

## 🔷 Project Significance

This project serves as a **hardware-level exploration of PLLs**, transforming abstract concepts into measurable electrical behavior. It provides a strong foundation for advanced topics such as:

* High-frequency PLL design
* Digital PLLs (FPGA-based)
* Control system modeling and stability analysis

---

## 🔷 Status

🚧 In development — includes schematic design, PCB layout, and experimental validation.

---

## 🔷 Author

Omkar Tikekar
Electronics & Telecommunication Engineering

---

