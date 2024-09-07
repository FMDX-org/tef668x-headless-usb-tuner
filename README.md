# TEF668X Headless USB Tuner

USB radio tuner based on STM32F072 MCU and TEF6687 RF receiver with digital audio and three antenna inputs (2x FM SMA & 1x AM U.FL).

Copyright (C) 2024  FMDX.org

# Firmware

See [FM-DX-Tuner](https://github.com/kkonradpl/FM-DX-Tuner).

# Audio output

The baseline version of the tuner supports only digital audio over USB. For a regular analog audio line-out, see the [Audiohat for Headless TEF](https://github.com/PE5PVB/Audiohat-Headless-TEF/).

# Important remarks

- TEF6687 chip is recommended for the best performance (FMSI, FULL SCAN RDS).
- RF circuits should contain NP0 (C0G) capacitors.
- Only V205 version of TEF668X supports the 55.46667 MHz crystal.
- For a crystal different than 55.46667 MHz, GPIO1 must be pulled to the ground (instead of pull-up).
