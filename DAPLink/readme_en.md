# DAPLink / CMSIS-DAP

[中文](./readme.md) | **English**

Collection of debuggers based on the ARM CMSIS-DAP protocol, split into **wired** and **wireless** categories.

## Categories

| Category | Subprojects | Status |
|----------|-------------|--------|
| [Wireless](<./Wireless/readme_en.md>) | [ch32v208](<./Wireless/ch32v208/readme_en.md>) ✅recommended / [ch32v307](<./Wireless/ch32v307/readme_en.md>) / [esp32s3](<./Wireless/esp32s3/readme_en.md>) | 🔗 Open-source project links + notes |
| [wired](<./wired/readme_en.md>) | [STM23F103x](<./wired/STM23F103x/readme_en.md>) / [CH552](<./wired/CH552/readme_en.md>) / [cmsis_dap_tcp_esp32](<./wired/cmsis_dap_tcp_esp32/readme_en.md>) | ✅ STM32F103 version complete |

## Quick picks

- Want **wireless debugging** → [ch32v208](<./Wireless/ch32v208/readme_en.md>) (newest design, recommended)
- Want a **DIY wired CMSIS-DAP board** → [STM23F103x](<./wired/STM23F103x/readme_en.md>) (complete Keil source + Altium projects)
- Want **remote debugging over the network** → [cmsis_dap_tcp_esp32](<./wired/cmsis_dap_tcp_esp32/readme_en.md>)

## Related links

- [Official DAPLink repository](https://github.com/ARMmbed/DAPLink)
- [CMSIS-DAP specification](https://arm-software.github.io/CMSIS_5/DAP/html/index.html)
