# vending_machine

# 🧾 Vending Machine Controller – Verilog HDL

This project implements a **Vending Machine Controller** using **Verilog HDL**, designed to operate in both configuration and operational modes. The controller supports up to **1024 items** and accepts currency denominations up to **₹100**, making it scalable and suitable for real-world embedded vending applications.


![image](https://github.com/user-attachments/assets/53393cd8-e357-4a9f-8ec1-de2218cdef0d)

This image explains the block diagram of vending machine 


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

This register array or memory represents 31-bit wide for each item and the total elements
MAX_ITEMS worth of entries.
Example: if the Vending machine can support up to 32 items then the register array is
Item_cfg[0] - 0x4000_0004
Item_cfg[1] - 0x4000_0004 + 4
Item_cfg[2] - 0x4000_0004 + 8
…
Item_cfg[31] - 0x4000_0004 + 31*4
This array lists full possible MAX_ITEMS per design, however use case can have less items
based on customer programming. I.e. no_of_items <= MAX_ITEMS.
So even though the register array or memory has MAX_ITEMS worth of entries, only the
no_items worth of entries are valid.
Each entry contains below:
Bits Field Type Description
31:24 disp_items RO The number of items, dispensed so far
23:16 avail_items RW The number of items, are loaded/available as of now
15:0 item_val RW This field holds the value of this item

## 🧪 Simulated Using

- **Vivado Design Suite** – for synthesis and behavioral simulation
## 📦 Use Case

This design can be used for:
- FPGA-based vending systems
- Educational labs on digital design and embedded systems
- RTL-level prototyping of real-time controllers

## 📚 Project Highlights

- Designed with industry-level structure
- Implements real-time event handling and change-return mechanism
- Ensures glitch-free operation across different clock domains
