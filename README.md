# 4-Bit Full Adder Using ATmega16

![Project Overview](images/adder_logic_gates.png)

This project implements a **4-bit Full Adder** using the **ATmega16 microcontroller**. It computes the sum and carry-out for two 4-bit binary inputs along with a carry-in signal. The results are displayed using LEDs connected to the microcontroller.

---

## ✨ Features
- **4-bit Binary Addition**:
  - Adds two 4-bit numbers (A and B) with a carry-in (Cin).
  - Outputs the Sum and Carry-out (Cout) on LEDs.
- **Dynamic Input Handling**:
  - Reads inputs directly from PORTA, PORTB, and PINB.
- **Assembly Language Implementation**:
  - Efficient and optimized for microcontroller use.

---

## 📋 Table of Contents
1. [Overview](#overview)
2. [Requirements](#requirements)
3. [Setup Instructions](#setup-instructions)
4. [How It Works](#how-it-works)
5. [Project Diagrams](#project-diagrams)
6. [References](#references)
7. [License](#license)

---

## 🛠️ Requirements

### Hardware:
- **ATmega16 Microcontroller** //1MHz internal clock used here
- LEDs (5) with 330 Ω resistors
- Push buttons (for binary inputs)
- Breadboard and jumper wires
- 5V Power Supply

### Software:
- [AVR Studio](https://www.microchip.com/mplab/avr-support/atmel-studio-7) (for compiling the code)
- [Proteus](https://www.labcenter.com/) (for circuit simulation)
- [AVRDUDE](http://savannah.nongnu.org/projects/avrdude/) (for programming the microcontroller)

---

## 🚀 Setup Instructions

1. **Assemble the Circuit**:
   - Connect inputs (A, B, and Cin) to **PORTA**, **PORTB**, and **PINB**, respectively.
   - Connect outputs (Sum and Carry) to **PORTC**, where LEDs are attached.
   - Use pull-down resistors with input buttons for stable signals.

2. **Load the Assembly Code**:
   - Open `4bit_full_adder.asm` in AVR Studio.
   - Compile the file to generate the `.hex` file.

3. **Program the Microcontroller**:
   - Use a suitable programmer (e.g., USBasp) to flash the `.hex` file to the ATmega16.

4. **Run the Simulation**:
   - Simulate the circuit using Proteus to validate functionality.
   - Test the hardware circuit with various input combinations.

---

## ⚙️ How It Works

1. **Initialization**:
   - Input ports (PORTA and PORTB) are configured as inputs.
   - Output port (PORTC) is configured to drive LEDs.

2. **Input Handling**:
   - Binary values for A and B are read from PORTA and PORTB.
   - Cin is derived from the 5th bit of PINB (via `SBRC` and `SBRS` instructions).

3. **Calculation**:
   - A, B, and Cin are added using the `ADD` instruction.
   - Carry-out is detected using bitwise operations.

4. **Output Display**:
   - Sum and Carry-out values are written to PORTC, lighting up the corresponding LEDs.

---

## 📊 Project Diagrams

### Circuit Diagram
![Circuit Diagram](images/circuit_diagram.png)

### Flowchart
![Flowchart](images/flowchart.jpg)

### Pinout Diagram
![Pinout](images/pinout.png)

---
