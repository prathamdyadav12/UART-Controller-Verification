# 🧩 Verification of APB-Based UART Master Core RTL

## 📘 Overview

This project focuses on the **functional verification of an APB-based UART Master Core RTL**.
 The verification is carried out using a **UVM (Universal Verification Methodology)** environment designed to ensure the correctness, reliability, and robustness of UART operation under various test scenarios.

Two UART cores are instantiated and connected to simulate **data transmission and reception**. The verification ensures that all UART functionalities perform as expected and comply with the APB protocol.

---

## 📁 File Structure

```diff
+---docs
|       block_diagram.png
|       coverage.png
|       tb_architecture.png
|       terminal_output.png
|       uart_data_frame.png
|       wave_form.png
|
+---rtl
|       uart_16550.v
|       uart_fifo.v
|       uart_if.sv
|       uart_register_file.v
|       uart_rx.v
|       uart_tx.v
|
+---sim
|       Makefile
|
+---tb
|       uart_assertions.sv
|       uart_env.sv
|       uart_env_config.sv
|       uart_sb.sv
|       uart_tb_top.sv
|       v_sequence.sv
|       v_sequencer.sv
|
+---test
|       uart_pkg.sv
|       uart_test_lib.sv
|
+---uart_agt_top
        uart_agent.sv
        uart_agt_config.sv
        uart_agt_top.sv
        uart_driver.sv
        uart_monitor.sv
        uart_sequence.sv
        uart_sequencer.sv
        uart_trans.sv
```

---

## 🔌 APB Protocol Overview

The **Advanced Peripheral Bus (APB)** is a part of ARM’s AMBA (Advanced Microcontroller Bus Architecture) family.
 It is designed for connecting low-bandwidth peripherals that do not require high performance.

### Key Features:

- Simple and low power consumption
- Supports **read and write** operations
- Uses a **two-phase protocol** (setup and enable phase)
- Synchronous operation with a single clock

---

## 📡 UART Overview

The **Universal Asynchronous Receiver-Transmitter (UART)** is a serial communication protocol widely used in embedded systems.
 It converts parallel data from the CPU into serial form for transmission and vice versa for reception.

### Basic Operation:

- **TX (Transmit)**: Converts parallel data to serial form
- **RX (Receive)**: Converts received serial data to parallel form
- Communication happens asynchronously (no shared clock)

### Applications:

- Serial communication between microcontrollers and PCs
- Debug consoles and data logging
- Communication with wireless modules (Bluetooth, GPS, etc.)

### Drawbacks:

- Limited distance and data rate
- No built-in error correction beyond parity check
- Requires precise baud rate synchronization

---

## 🧱 Testbench Architecture
<img width="2978" height="2477" alt="image" src="https://github.com/user-attachments/assets/7db31245-5ceb-4de4-8db7-860ad465a12c" />


---

## 🧪 Test Cases

Nine major test scenarios were verified to ensure full UART functionality:

| Test Case           | Description                                                 |
| ------------------- | ----------------------------------------------------------- |
| **Full-Duplex**     | Simultaneous TX and RX verification                         |
| **Half-Duplex**     | Transmission and reception in an alternate fashion          |
| **Loopback**        | Internal loopback testing of data integrity                 |
| **Parity Error**    | Verification of parity bit detection and reporting          |
| **Break Error**     | Checking for a continuous low-line condition                |
| **Overrun Error**   | Buffer overflow handling                                    |
| **Framing Error**   | Incorrect data frame configuration condition                |
| **THR Empty Error** | Validation of the transmit holding register empty condition |
| **Timeout Error**   | A smaller number of data characters received                |

---

## 📊 Results & Coverage

- ✅ **100% Functional Coverage Achieved**
- ✅ All Assertions Passed
- ✅ Verification goals and protocol compliance met

### Coverage Summary
<img width="1919" height="872" alt="image" src="https://github.com/user-attachments/assets/e04b5a78-b9c9-4c67-8f5f-931b40c1d042" />


### UART Data Frame

![Data Frame](docs/uart_data_frame.png)

### Waveform Example

<img width="884" height="434" alt="image" src="https://github.com/user-attachments/assets/12c8a754-ada1-4b5e-a026-a40fe6bcb320" />


### Terminal Output

![Output](docs/terminal_output.png)

---

## 📚 References

- ARM AMBA APB Protocol Specification
- UVM 1.2 Reference Guide
- UART 16550 Datasheet
- Mentor QuestaSim & Synopsys VCS Documentation

---

## 🏁 Conclusion

This project successfully verified the **APB-based UART Master Core RTL** using a **UVM-based testbench**, achieving **95% functional coverage** across multiple UART operation modes and error conditions.
 The verification environment is scalable for integrating more agents and extending coverage for advanced UART configurations.
