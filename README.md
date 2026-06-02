# FIR Filter Design in Verilog

## Overview

This project implements a **Finite Impulse Response (FIR) Filter** in Verilog HDL. The design generates a sine wave input using a phase accumulator and phase-to-amplitude converter, then processes the signal through an FIR filter to produce a filtered output.

The project includes:

* Top-level FIR filter module
* Testbench for simulation
* Sine wave generation
* FIR filtering of the generated signal

---

## Project Structure

```text
├── top.v          # Top-level FIR filter module
├── testbench.v    # Testbench for simulation
└── README.md
```

---

## Module Description

### FIR_filter (Top Module)

The top-level module integrates three major blocks:

1. **Phase Accumulator**

   * Generates phase values.
   * Operates using the system clock.

2. **Phase-to-Amplitude Converter**

   * Converts phase information into sine wave amplitude values.
   * Produces an 8-bit sine wave output.

3. **FIR Filter**

   * Accepts the generated sine wave as input.
   * Produces the filtered output.

### Inputs

| Signal | Width | Description  |
| ------ | ----- | ------------ |
| clock  | 1 bit | System clock |
| reset  | 1 bit | Reset signal |

### Outputs

| Signal   | Width   | Description                 |
| -------- | ------- | --------------------------- |
| data_sin | 8 bits  | Generated sine wave samples |
| Data_Out | 17 bits | FIR filtered output         |

---

## Simulation

The testbench performs the following:

* Generates a clock signal.
* Applies a reset pulse.
* Instantiates the FIR filter module.
* Displays input and filtered output values during simulation.
* Stops the simulation automatically after a predefined time.

Example simulation output:

```text
Time: 1500, Data_sin: 25, Filtered_Output: 18
Time: 2500, Data_sin: 48, Filtered_Output: 35
Time: 3500, Data_sin: 72, Filtered_Output: 58
```

---

## Running the Simulation

### Using ModelSim

```bash
vlog top.v testbench.v
vsim testbench_fir
run -all
```

### Using Icarus Verilog

```bash
iverilog -o fir_sim top.v testbench.v
vvp fir_sim
```

---

## Features

* Verilog HDL implementation
* Modular design approach
* Sine wave signal generation
* FIR filtering operation
* Simulation-ready testbench
* Easy integration into FPGA-based DSP systems

---

## Applications

* Digital Signal Processing (DSP)
* Audio Signal Filtering
* Noise Reduction
* Communication Systems
* FPGA-Based Signal Processing

---

## Author

Sanjay SD

## License

This project is provided for educational and learning purposes.
