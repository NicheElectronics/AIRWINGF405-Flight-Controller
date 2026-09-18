# AIRWINGF405 Flight Controller

A custom **six-layer flight-controller PCB** centered on the **STM32F405**. The design combines a **BMI270 IMU**, **SPA03-006 barometer**, flash memory, power regulation and interfaces for a multirotor flight-control system.

> **Status:** The custom PCB has **not** been fabricated or flight tested. Firmware and configuration work, including an LED-strip demonstration on a separate development board, should not be interpreted as validation of the AIRWINGF405 hardware.

## Hardware overview

| Block | Design |
| --- | --- |
| Main MCU | STM32F405 |
| Motion sensing | BMI270 accelerometer and gyroscope |
| Pressure sensing | SPA03-006 barometer |
| Storage | On-board flash memory |
| Connectivity | USB, UART, SPI and I²C interfaces |
| Flight I/O | Motor/ESC interfaces and other flight-controller connections |
| Power | DC-DC and LDO stages, with filtering and local decoupling |
| CAD / PCB | EasyEDA, six-layer board |

For exact pad assignments, voltages, supported peripherals and connector orientation, use the schematic for the board revision being assembled. The [STM32F405 product page](https://www.st.com/en/microcontrollers-microprocessors/stm32f405-415.html) and [BMI270 datasheet](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmi270-ds000.pdf) provide component-level details.

## Firmware work

The repository includes **Betaflight** and **ArduPilot** target/configuration work for the proposed board. These files are development artifacts; compatibility with a fabricated AIRWINGF405 PCB remains to be checked. A Betaflight LED-strip photo/video was made using a **development board**, not the custom flight-controller PCB.

Do not assume a firmware target or pin map is ready for flight solely because configuration files are present. Confirm sensor buses, motor outputs, UARTs, flash, barometer and LED assignments against the final schematic before using a target on assembled hardware.

## Planned hardware bring-up

1. Review the schematic, PCB, manufacturing files and assembly orientation.
2. Check all rails for shorts; power an assembled board with current limiting and verify the DC-DC/LDO outputs.
3. Connect a debugger or USB as appropriate and confirm the STM32F405 boots reliably.
4. Verify IMU, barometer and flash communication, then each UART and peripheral interface.
5. Verify motor/ESC outputs with **propellers removed** and confirm the mapping in the chosen firmware target.
6. Record measured power, sensor and interface results before any controlled flight test.

Until those steps are completed, this repository documents a **designed flight controller and firmware development work**, not a flight-proven board.

## Author

**Nishant Patil**

No license has been specified for the project files. Add one if you want to define reuse terms.
