# UARTVERIFICATION


# UART SystemVerilog Design and Testbench

## Overview

This repository contains the SystemVerilog implementation of a UART (Universal Asynchronous Receiver-Transmitter) module, including its testbench for simulation. The design includes both UART transmitter and receiver modules and integrates them into a top-level module for testing. Additionally, a comprehensive testbench with classes for transactions, generator, driver, monitor, and scoreboard is provided to validate the UART functionality.

## Directory Structure

├── rtl


│ ├── uart_top.sv

│ ├── uarttx.sv

│ ├── uartrx.sv

├── tb

│ ├── transaction.sv

│ ├── generator.sv

│ ├── driver.sv

│ ├── monitor.sv

│ ├── scoreboard.sv

│ ├── environment.sv

│ ├── tb.sv

│ ├── uart_if.sv

├── README.md


## Files Description

### RTL

- **uart_top.sv**: Top-level module integrating the UART transmitter and receiver.
- **uarttx.sv**: UART transmitter module.
- **uartrx.sv**: UART receiver module.

### Testbench

- **transaction.sv**: Defines the transaction class for UART operations.
- **generator.sv**: Generates random transactions for the UART module.
- **driver.sv**: Drives the UART interface with generated transactions.
- **monitor.sv**: Monitors the UART interface and captures the transactions.
- **scoreboard.sv**: Compares the expected and actual results to verify correctness.
- **environment.sv**: Instantiates and connects the generator, driver, monitor, and scoreboard.
- **tb.sv**: Top-level testbench module.
- **uart_if.sv**: UART interface definition.

## Getting Started

### Prerequisites

To simulate the design, you will need a SystemVerilog simulation tool such as ModelSim, VCS, or XSim.

### Compilation and Simulation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/uart-sv-design.git
    cd uart-sv-design
    ```

2. **Compile the design and testbench:**

    For ModelSim:
    ```sh
    vlib work
    vlog rtl/uart_top.sv rtl/uarttx.sv rtl/uartrx.sv tb/transaction.sv tb/generator.sv tb/driver.sv tb/monitor.sv tb/scoreboard.sv tb/environment.sv tb/tb.sv tb/uart_if.sv
    ```

3. **Run the simulation:**

    For ModelSim:
    ```sh
    vsim tb
    ```

### Viewing the Waveforms

To view the waveforms generated during the simulation, use the following commands:

1. **Open ModelSim:**
    ```sh
    vsim tb
    ```

2. **Run the simulation and view the waveforms:**
    ```sh
    run -all
    ```

3. **Open the waveform window:**
    ```sh
    view wave
    ```

4. **Add signals to the waveform window:**
    ```sh
    add wave tb/*
    ```

## Design Details

### UART Top Module (uart_top.sv)

The `uart_top` module instantiates both the UART transmitter (`uarttx`) and receiver (`uartrx`) modules. The module parameters `clk_freq` and `baud_rate` are used to configure the clock frequency and baud rate for UART communication.

### UART Transmitter (uarttx.sv)

The `uarttx` module handles the transmission of data over the UART interface. It includes a state machine to manage the transmission process and generates the appropriate UART clock.

### UART Receiver (uartrx.sv)

The `uartrx` module handles the reception of data over the UART interface. It includes a state machine to manage the reception process and generates the appropriate UART clock.

### Testbench

The testbench is structured using the Universal Verification Methodology (UVM) principles, with separate classes for generating, driving, monitoring, and checking the transactions. The `environment` class connects all these components, and the `tb` module instantiates the DUT and the environment.

## Contributions

Contributions to enhance the functionality or improve the verification environment are welcome. Please fork the repository and create a pull request with your changes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.


