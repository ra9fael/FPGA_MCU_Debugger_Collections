# FPGA / MCU Debugger Collections

[中文](./readme.md) | **English**

Collection of hardware design files (schematics, PCB), firmware, and build tutorials for DIY FPGA / MCU debuggers, logic analyzers, and wireless serial tools.

[![GitHub issues](https://img.shields.io/github/issues/konosubakonoakua/FPGA_MCU_Debugger_Collections)](https://github.com/konosubakonoakua/FPGA_MCU_Debugger_Collections/issues)

**Note: this project is for educational and research purposes only.**

---

## Table of Contents

- [Category Overview](#category-overview)
- [Repository Structure](#repository-structure)
- [Work in Progress](#work-in-progress)
- [General Build Guide](#general-build-guide)
- [Required Tools](#required-tools)
- [Notes](#notes)
- [Contributing](#contributing)
- [Related Links](#related-links)

---

## Category Overview

| Category | Description | Subprojects | Status |
|----------|-------------|-------------|--------|
| [JLink](<./JLink/readme_en.md>) | Hardware references and official resources | V9 / OB 072 / OB F103 / historical design notes | Hardware references only |
| [STLink](<./STLink/readme_en.md>) | ST-LINK mods & DIY | V2-1 mod / V3 / V3 Mini | ✅ V2-1 complete, V3 🚧 |
| [DAPLink](<./DAPLink/readme_en.md>) | CMSIS-DAP series | Wired (STM32F103/CH552/ESP32) + Wireless (ch32v208 recommended/ch32v307/esp32s3) | ✅ Complete |
| [BlackMagic](<./BlackMagic/readme_en.md>) | Black Magic Probe | Official + MioLink (RP2040) | 🔗 Links only |
| [JTAG-FTDI](<./JTAG-FTDI/readme_en.md>) | Xilinx FTDI JTAG | hw-ftdi-jtag-xilinx (submodule, FT2232HQ) | ✅ Complete |
| [Xilinx Virtual Cable (XVC)](<./Xilinx Virtual Cable (XVC)/readme_en.md>) | JTAG over network (XVC) | xvc-pico / jtag-remote-server | 🔗 Links only |
| [USBBlaster](<./USBBlaster/readme_en.md>) | Altera/Intel FPGA programmer | CH552Nano | 🔗 Links only |
| [MiniWiggler](<./MiniWiggler/readme_en.md>) | Infineon 3-in-1 programmer | DAP + JTAG + UART | ✅ Complete |
| [Logic Analyzer](<./Logic Analyzer/readme_en.md>) | Logic analyzers | CH32H417 / CY7C68013A / Rpi Pico | 🔗 Links only |
| [Serial Port Wireless](<./Serial Port Wireless/readme_en.md>) | Wireless serial port | CH570 | ✅ Complete |

---

## Repository Structure

```
FPGA_MCU_Debugger_Collections/
├── JLink/                              # Hardware references and official resources
│   ├── JlinkV9/                        #   J-Link V9 (LPC4322)
│   ├── JlinkV9 mini/                   #   Ultra-compact V9 (STM32F205)
│   ├── JlinkV9 isoloated/              #   Isolated V9
│   ├── Jlink OB 072/                   #   J-Link OB (STM32F072)
│   ├── J-Link OB-STM32F103 V1/         #   J-Link OB (STM32F103C8T6)
│   └── JLink converted to STLINK V2 V2-1/  # Official conversion resources
├── STLink/                             # ST-LINK series
│   ├── STLINKV2-1/                     #   V2 modded to V2-1 (with st-decrypt tool)
│   └── STLINKV3/                       #   V3 (MB1367 reference design) + v3 mini
├── DAPLink/                            # CMSIS-DAP series
│   ├── wired/                          #   Wired: STM23F103x / CH552 / cmsis_dap_tcp_esp32
│   └── Wireless/                       #   Wireless: ch32v208 (recommended) / ch32v307 / esp32s3
├── BlackMagic/                         # Black Magic Probe (links)
├── JTAG-FTDI/
│   └── hw-ftdi-jtag-xilinx/            # Xilinx FTDI JTAG (Git submodule)
├── Xilinx Virtual Cable (XVC)/         # JTAG over network (links)
├── USBBlaster/                         # USB Blaster (CH552, links)
├── MiniWiggler/                        # Infineon 3-in-1 programmer
├── Logic Analyzer/                     # Logic analyzers: CH32H417 / CY7C68013A / Rpi Pico
├── Serial Port Wireless/               # Wireless serial: CH570
├── readme.md                           # Chinese version
└── readme_en.md                        # This file (English)
```

See each subfolder's readme for chip choices, file manifests, and build steps.

---

## Work in Progress

The following projects are incomplete — contributions welcome:

| Project | Status | Progress |
|---------|--------|----------|
| [ARM-Mbed DAPLink](<./DAPLink/wired/STM23F103x/readme_en.md>) | Incomplete | Schematic + PCB (Altium) uploaded, firmware pending |
| [BlackMagic Probe](<./BlackMagic/readme_en.md>) | Incomplete | Official project links only |
| [ST-LINK V3](<./STLink/STLINKV3/readme_en.md>) | Incomplete | MB1367 reference schematic uploaded, firmware pending |

---

## General Build Guide

These steps apply only to subprojects with firmware you are authorized to obtain and use. The JLink collection provides hardware references, not a complete debugger build procedure.

### Preparation

1. Order PCBs for your chosen project (JLCPCB recommended)
2. Solder all components
3. Have a working SWD programmer ready (ST-LINK / J-Link / DAP-Link)

### Flash the Bootloader

1. Connect the programmer to the target board via SWD
2. Erase the chip with the appropriate tool:
   - STM32CubeProgrammer / ST-LINK Utility
   - J-Flash
   - OpenOCD
3. Flash the bootloader to the chip's base address

### Flash the Firmware

Methods differ per debugger (see each subfolder readme):

- **ST-LINK V2-1**: automatic upgrade via ST-LINK Utility → Firmware Update → [STLink/STLINKV2-1](<./STLink/STLINKV2-1/readme_en.md>)
- **CMSIS-DAP**: directly flash the firmware built from the Keil project → [DAPLink/wired/STM23F103x](<./DAPLink/wired/STM23F103x/readme_en.md>)


---

## Required Tools

### Hardware

- SWD programmer (any working debugger)
- Soldering iron + solder (hand soldering; a knife-tip iron is recommended)
- Multimeter (for troubleshooting solder joints)

### Software

| Tool | Purpose |
|------|---------|
| [J-Link Commander](https://www.segger.com/downloads/jlink/) | Use with devices covered by the vendor license |
| [ST-LINK Utility / STM32CubeProgrammer](https://www.st.com) | ST-LINK firmware flashing |
| [Altium Designer / KiCad](https://www.kicad.org) | View/edit PCB projects |
| [Keil MDK](https://www.keil.com) | Build CMSIS-DAP source |
| [MounRiver Studio](http://www.mounriver.com/) | Build CH32-series source (wireless DAPLink, CH570, etc.) |
| [FT_Prog](https://ftdichip.com/utilities/) | FTDI chip configuration (MiniWiggler, FTDI JTAG) |
| [Sigrok PulseView](https://sigrok.org/wiki/PulseView) | Logic analyzer host software |
| [OpenOCD](https://openocd.org) | General debugger toolchain |

---

## Notes

### Sources, licenses and trademarks

The JLink collection contains hardware reference material and links to official documentation. It does not distribute J-Link software, firmware, extraction utilities or license-bypass procedures. Other subprojects have their own sources and license conditions.

Existing author attribution and licenses remain applicable. Files without an explicit license are not automatically licensed for reuse or redistribution; confirm permission with the relevant rightsholder.

This project is not affiliated with or endorsed by SEGGER or STMicroelectronics. J-Link, ST-LINK, Arm and CMSIS are names or trademarks of their respective owners. Obtain vendor software through official channels and follow its applicable license.

### Other Notes

- The STM32F103C8T6 comes in 64KB and 128KB flash variants; some firmware may require the 128KB variant
- Soldering 0402 components takes some experience; a knife-tip iron is recommended
- If the device is not recognized, check soldering and power first, then the SWD connection

---

## Contributing

Issues and pull requests welcome.

For J-Link contributions, include the source and redistribution permission for hardware files. Do not submit proprietary firmware, vendor software copies, extraction utilities, license-bypass instructions, or archives containing those materials. Review archive contents and screenshots as well as text.

- Found a bug or problem → file an [Issue](https://github.com/konosubakonoakua/FPGA_MCU_Debugger_Collections/issues)
- Want to complete an unfinished project → contact the author or submit a PR

---

## Related Links

- [J-Link official](https://www.segger.com)
- [ST-LINK official](https://www.st.com)
- [CMSIS-DAP specification](https://arm-software.github.io/CMSIS_5/DAP/html/index.html)
- [DAPLink official](https://github.com/ARMmbed/DAPLink)
- [BlackMagic Probe official](https://black-magic.org)
- [OpenOCD](https://openocd.org)
- [WCH](https://www.wch.cn)
- [Sigrok](https://sigrok.org)
