Verification of APB-Based UART Master Core RTL

📘 Overview

This project focuses on the functional verification of an APB-based UART Master Core RTL. The verification is carried out using a UVM (Universal Verification Methodology) environment designed to ensure the correctness, reliability, and robustness of UART operation under various test scenarios.

Two UART cores are instantiated and connected to simulate data transmission and reception. The verification ensures that all UART functionalities perform as expected and comply with the APB protocol.
📘  File Structure
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
