# Wired DAPLink / CMSIS-DAP Designs

[中文](./readme.md) | **English**

Wired debugger designs based on the CMSIS-DAP protocol.

## Subprojects

| Subproject | MCU/Approach | Description | Status |
|------------|--------------|-------------|--------|
| [STM23F103x](<./STM23F103x/readme_en.md>) | STM32F103C8T6 | CMSIS-DAP (SWD+SWO+VCP, Keil source + Altium projects); includes ARM-Mbed DAPLink hardware project | ✅ Complete (DAPLink firmware pending) |
| [CH552](<./CH552/readme_en.md>) | CH552 | wagiminator's open-source CMSIS-DAP (SWD+JTAG+VCP) | 🔗 Links only |
| [cmsis_dap_tcp_esp32](<./cmsis_dap_tcp_esp32/readme_en.md>) | ESP32 | CMSIS-DAP over TCP/IP, remote debugging with OpenOCD over the network | 🔗 Links only |
