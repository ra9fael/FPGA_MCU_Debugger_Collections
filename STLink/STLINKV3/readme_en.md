# ST-LINK V3 Build

[中文](./readme.md) | **English**

> **Status: incomplete.** Currently only ST's official reference design is collected; firmware and a custom PCB are pending. Contributions welcome.

## Current progress

- ST official reference design schematic (MB1367) uploaded
- Firmware and custom PCB not yet organized

## File manifest

| File | Description |
|------|-------------|
| [MB1367C/mb1367.pdf](./MB1367C/mb1367.pdf) | ST official MB1367 reference schematic |
| `MB1367C/MB1367C.7z` | ST official MB1367C reference design project |
| [v3 mini/](<./v3 mini/readme_en.md>) | V3 Mini open-source design (schematic + BOM PDFs) |

## Hardware specifications

ST-LINK V3 is ST's latest-generation debugger:

- **MCU**: STM32F723IE (Cortex-M7)
- **Interfaces**: SWD + JTAG + VCP + bridge functions (SPI/I2C/CAN/GPIO)
- **Max SWD frequency**: 24 MHz
- **Features**: STDC14 connector plus legacy JTAG/SWD pin headers

## TODO

- [ ] Organize and upload firmware
- [ ] Design a custom PCB
- [ ] Write a build tutorial

## Related links

- [ST-LINK V3SET official page](https://www.st.com/zh/development-tools/stlink-v3set.html)
- [ST-LINK MB1367 reference design](https://www.st.com)
