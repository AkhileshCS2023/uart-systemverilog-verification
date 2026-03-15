# UART Verification using SystemVerilog

## Project Overview

This project implements a **UART (Universal Asynchronous Receiver Transmitter) design and verification environment** using **SystemVerilog**.
A modular **layered testbench architecture** is developed to verify the functionality of the UART transmitter and receiver.

The verification environment generates stimulus, monitors DUT outputs, compares results using a reference model, and checks correctness through a scoreboard.

The project demonstrates fundamental **SoC verification concepts** such as transaction-based verification, modular testbench components, and functional checking.

---

## Design Under Test (DUT)

The DUT consists of the following RTL modules:

* **uart_top.v** – Top-level UART module
* **uart_tx.v / uart_sender.v** – UART transmitter logic
* **uart_rx.v** – UART receiver logic
* **baud_rate_generator.v** – Generates the baud clock for UART communication

The UART performs **serial communication using start bit, data bits, and stop bit** according to the standard UART protocol.

---

## Verification Architecture

The testbench follows a **layered architecture** commonly used in SystemVerilog verification.

Components used:

* **Transaction** – Defines the UART packet structure
* **Generator** – Generates random UART transactions
* **Driver** – Drives stimulus to the DUT via interface
* **Monitor** – Observes DUT signals and captures outputs
* **Reference Model** – Predicts expected results
* **Scoreboard** – Compares expected vs actual outputs
* **Environment** – Connects all verification components
* **Test** – Controls simulation flow

Verification flow:

Generator → Driver → DUT → Monitor → Scoreboard → Result Check

---

## Testbench Components

| File                    | Description                          |
| ----------------------- | ------------------------------------ |
| uart_transaction.sv     | Defines UART transaction packet      |
| uart_generator.sv       | Generates stimulus transactions      |
| uart_driver.sv          | Drives transactions to DUT           |
| uart_monitor.sv         | Observes DUT outputs                 |
| uart_reference_model.sv | Predicts expected behavior           |
| uart_scoreboard.sv      | Compares expected and actual results |
| uart_environment.sv     | Connects verification components     |
| uart_test.sv            | Test scenario                        |
| uart_interface.sv       | Interface between DUT and testbench  |
| uart_package.sv         | Contains shared definitions          |

---

## Simulation

Simulation is performed using **QuestaSim**.

### Steps

1. Compile RTL and SystemVerilog files
2. Run the testbench
3. Observe waveform and scoreboard results

The monitor captures DUT outputs and the scoreboard verifies correctness of transmitted and received data.

---

## Expected Results

* UART data transmission should match the expected transaction data.
* Scoreboard verifies correctness of each transaction.
* Waveforms confirm proper UART timing and data transfer.

---

## Tools Used

* SystemVerilog
* QuestaSim Simulator
* GitHub (version control)

---

## Learning Outcomes

Through this project the following verification concepts are demonstrated:

* Transaction-based verification
* Layered testbench architecture
* Driver and monitor implementation
* Scoreboard-based checking
* Reference model validation
* UART protocol understanding

---

## Author

Akhilesh
Electronics and Communication Engineering
