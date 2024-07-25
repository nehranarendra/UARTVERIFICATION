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
