# TEF668X Headless USB Tuner

USB radio tuner based on STM32F072 MCU and TEF6687 RF receiver with three antenna inputs and digital audio.

Copyright (C) 2024 FMDX.org

You may redistribute and modify this source under the terms of the CERN-OHL-W v2 (see LICENSE file).

# Credits 

- Konrad Kosmatka - HW & FW architecture and development
- Sjef Verhoeven - HW development
- Marek Kraus - HW & FW prototyping
- Marek Farkaš - testing and integration with FM-DX Webserver
- Przemysław Korpas - HW consultation, reviews
- Sebastian Białkowski - HW consultation, reviews

# Firmware

The firmware is available in a separate repository: [FM-DX-Tuner](https://github.com/kkonradpl/FM-DX-Tuner).

Firmware dependencies:
- Board: STM32 MCU Based Boards ([STM32duino](https://github.com/stm32duino)) - download using board manager
- Library: [TinyUSB](https://github.com/hathach/tinyusb) - install manually to the Arduino libraries

During first firmware flashing, short BOOT to 3.3V, plug the USB cable and flash using Arduino IDE (DFU method). Once the firmware is running, it is not necessary to manually short BOOT pin. See [tef-bootloader](https://github.com/kkonradpl/tef-bootloader).

# Audio output

The baseline version of the tuner supports only digital audio over USB. For a regular analog audio line-out, see the [Audiohat for Headless TEF](https://github.com/PE5PVB/Audiohat-Headless-TEF/).

# Important remarks

- TEF6687/V205 (F8705) chip is recommended for the best performance (FMSI, FULL SCAN RDS).
- RF circuits should contain NP0 (C0G) capacitors.
- Only V205 version of TEF668X supports the 55.46667 MHz crystal.
- For a crystal different than 55.46667 MHz, GPIO1 must be pulled to the ground (instead of pull-up).
- All capacitors and resistors are 0603, except R30 and R31 which are 0402.
