# PureSTM-lib
A lightweight, bare-metal Hardware Abstraction Layer (HAL) for STM32F4 series microcontrollers, written in C without external dependencies.

--- 
## 🚀 Overview
PureSTM is a personal study project developed to explore the fundamentals of Bare-Metal embedded systems. Instead of relying on pre-built libraries like STM32 CubeHAL, this project focuses on direct communication with the ARM Cortex-M4 hardware through register manipulation.

The goal of this library is to document my learning journey in Computer Engineering, providing a hands-on understanding of memory mapping, peripheral initialization, and hardware-software interfacing.

## 🛠️ Key Learning Features
* Register-Level Access: Implementation of peripheral control by directly writing to memory addresses, based on the STM32F4 Reference Manual.

* Hardware Fundamentals: Deep dive into the RCC (Reset and Clock Control) to understand how to "wake up" and synchronize internal peripherals.

* GPIO Management: Learning the difference between registers like MODER, ODR, and BSRR for efficient digital I/O control.

* Timing & Cycles: Implementing precise software delays by configuring Hardware Timers, moving away from inaccurate "dummy loops".

* Low-Level Architecture: Hands-on experience with C structures for memory mapping and the use of volatile pointers to handle hardware-changed values.

## 📂 Project Structure
The project follows a modular organization to separate hardware-specific initialization from the peripheral library logic:

* src/: Contains the source files of the project:

* main.c: The entry point of the application where the logic (e.g., LED blinking) is implemented.

* pure_stm.c: The core of the library, containing the implementation of RCC, GPIO, and Timing functions.

* startup.c: The assembly-equivalent in C that defines the Interrupt Vector Table and calls the Reset_Handler.

* include/: Contains the header files:

  * pure_stm.h: Definitions for register structures, memory mapping (base addresses), and function prototypes.

* platformio.ini: The project configuration file that defines the build environment, including the target microcontroller, platform toolchain, and specific compiler flags (such as linker script paths and optimization levels) required for successful compilation and Proteus simulation.

## 📈 Roadmap
* Add UART support for serial debugging.

* Implement PWM functions for TIM9-11.

* Add ADC (Analog to Digital Converter) support.

* Implement HSE (External Crystal) clock configuration logic.
