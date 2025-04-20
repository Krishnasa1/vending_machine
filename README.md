# vending_machine

# 🧾 Vending Machine Controller – Verilog HDL

This project implements a **Vending Machine Controller** using **Verilog HDL**, designed to operate in both configuration and operational modes. The controller supports up to **1024 items** and accepts currency denominations up to **₹100**, making it scalable and suitable for real-world embedded vending applications.

## 🔧 Features

- ✅ **FSM-Based Control**: Finite State Machine manages reset, configuration, and operation modes.
- 🛠️ **APB Interface**: Supports configuration via APB protocol (using a 10 MHz clock).
- 🕒 **Clock Domain Crossing (CDC)**: Safely handles asynchronous currency inputs across clock domains.
- 💵 **Smart Currency Logic**: Validates currency and dispenses items or returns appropriate change.
- 📊 **Register Mapping**: Each item stores price, available stock, and number of items dispensed.
- 📈 **Scalable Design**: Parametrized for up to 1024 items and ₹100 denominations.
- 🔍 **Synthesizable RTL**: Fully synthesizable and simulation-ready in Vivado or ModelSim.

## 🧱 Modules

- `vending_machine.v`: Main controller integrating FSM, APB interface, and operation logic.
- `testbench.v`: Verification module for simulating different scenarios.
- Optional helper modules (e.g., FSM, currency_decoder) can be added as needed.

## 🧪 Simulated Using

- **Vivado Design Suite** – for synthesis and behavioral simulation
- **GTKWave / XSIM** – for waveform analysis and debugging

## 📦 Use Case

This design can be used for:
- FPGA-based vending systems
- Educational labs on digital design and embedded systems
- RTL-level prototyping of real-time controllers

## 📚 Project Highlights

- Designed with industry-level structure
- Implements real-time event handling and change-return mechanism
- Ensures glitch-free operation across different clock domains
