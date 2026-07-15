# FPGA / MCU Debugger Collections

**中文** | [English](./readme_en.md)

自制 FPGA / MCU 调试器、逻辑分析仪、无线串口工具的硬件设计资料（原理图、PCB）、固件与制作教程合集。

[![GitHub issues](https://img.shields.io/github/issues/konosubakonoakua/FPGA_MCU_Debugger_Collections)](https://github.com/konosubakonoakua/FPGA_MCU_Debugger_Collections/issues)

**使用前请核对各子项目的资料来源和许可。**

---

## 目录

- [分类总览](#分类总览)
- [仓库结构](#仓库结构)
- [进行中的项目](#进行中的项目)
- [通用制作步骤](#通用制作步骤)
- [所需工具](#所需工具)
- [注意事项](#注意事项)
- [贡献](#贡献)
- [相关链接](#相关链接)

---

## 分类总览

| 分类 | 说明 | 子项目 | 状态 |
|------|------|--------|------|
| [JLink](<./JLink/readme.md>) | 硬件参考与官方资料 | V9 / OB 072 / OB F103 / 历史设计说明 | 仅硬件参考 |
| [STLink](<./STLink/readme.md>) | ST-LINK 魔改与自制 | V2-1 魔改 / V3 / V3 Mini | ✅ V2-1 完整，V3 🚧 |
| [DAPLink](<./DAPLink/readme.md>) | CMSIS-DAP 系列 | 有线（STM32F103/CH552/ESP32）+ 无线（ch32v208 推荐/ch32v307/esp32s3） | ✅ 完整 |
| [BlackMagic](<./BlackMagic/readme.md>) | Black Magic Probe | 官方 + MioLink (RP2040) | 🔗 仅链接 |
| [JTAG-FTDI](<./JTAG-FTDI/readme.md>) | Xilinx FTDI JTAG | hw-ftdi-jtag-xilinx（子模块，FT2232HQ） | ✅ 完整 |
| [Xilinx Virtual Cable (XVC)](<./Xilinx Virtual Cable (XVC)/readme.md>) | 网络 JTAG (XVC) | xvc-pico / jtag-remote-server | 🔗 仅链接 |
| [USBBlaster](<./USBBlaster/readme.md>) | Altera/Intel FPGA 下载器 | CH552Nano | 🔗 仅链接 |
| [MiniWiggler](<./MiniWiggler/readme.md>) | 英飞凌三合一下载器 | DAP + JTAG + 串口 | ✅ 完整 |
| [Logic Analyzer](<./Logic Analyzer/readme.md>) | 逻辑分析仪 | CH32H417 / CY7C68013A / Rpi Pico | 🔗 仅链接 |
| [Serial Port Wireless](<./Serial Port Wireless/readme.md>) | 无线串口 | CH570 | ✅ 完整 |

---

## 仓库结构

```
FPGA_MCU_Debugger_Collections/
├── JLink/                              # 硬件参考与官方资料
│   ├── JlinkV9/                        #   J-Link V9 (LPC4322)
│   ├── JlinkV9 mini/                   #   超小型 V9 (STM32F205)
│   ├── JlinkV9 isoloated/              #   隔离版 V9
│   ├── Jlink OB 072/                   #   J-Link OB (STM32F072)
│   ├── J-Link OB-STM32F103 V1/         #   J-Link OB (STM32F103C8T6)
│   └── JLink converted to STLINK V2 V2-1/  # 官方转换资料索引
├── STLink/                             # ST-LINK 系列
│   ├── STLINKV2-1/                     #   V2 魔改 V2-1（含 st-decrypt 工具）
│   └── STLINKV3/                       #   V3（MB1367 参考设计）+ v3 mini
├── DAPLink/                            # CMSIS-DAP 系列
│   ├── wired/                          #   有线：STM23F103x / CH552 / cmsis_dap_tcp_esp32
│   └── Wireless/                       #   无线：ch32v208(推荐) / ch32v307 / esp32s3
├── BlackMagic/                         # Black Magic Probe（链接）
├── JTAG-FTDI/
│   └── hw-ftdi-jtag-xilinx/            # Xilinx FTDI JTAG（Git 子模块）
├── Xilinx Virtual Cable (XVC)/         # 网络 JTAG（链接）
├── USBBlaster/                         # USB Blaster（CH552，链接）
├── MiniWiggler/                        # 英飞凌三合一下载器
├── Logic Analyzer/                     # 逻辑分析仪：CH32H417 / CY7C68013A / Rpi Pico
├── Serial Port Wireless/               # 无线串口：CH570
├── readme.md                           # 本文件（中文）
└── readme_en.md                        # English version
```

各调试器的芯片方案、文件清单与制作步骤见对应子目录 readme。

---

## 进行中的项目

以下项目当前资料不完整，欢迎贡献：

| 项目 | 状态 | 当前进度 |
|------|------|----------|
| [ARM-Mbed DAPLink](<./DAPLink/wired/STM23F103x/readme.md>) | 未完成 | 原理图 + PCB (Altium) 已上传，固件待补 |
| [BlackMagic Probe](<./BlackMagic/readme.md>) | 未完成 | 仅收录官方项目链接 |
| [ST-LINK V3](<./STLink/STLINKV3/readme.md>) | 未完成 | MB1367 参考设计原理图已上传，固件待补 |

---

## 通用制作步骤

以下步骤仅适用于已取得合法固件及使用许可的子项目。JLink 分类仅提供硬件参考，不提供完整调试器制作流程。

### 准备

1. 根据所选项目打板（推荐嘉立创）
2. 焊接所有元器件
3. 准备一台可用的 SWD 编程器（ST-LINK / J-Link / DAP-Link）

### 刷写 Bootloader

1. 通过 SWD 接口连接编程器到目标板
2. 使用对应工具擦除芯片：
   - STM32CubeProgrammer / ST-LINK Utility
   - J-Flash
   - OpenOCD
3. 刷入 bootloader 固件到芯片起始地址

### 刷写固件

不同调试器方式不同（详见各子目录 readme）：

- **ST-LINK V2-1**：通过 ST-LINK Utility → Firmware Update 自动升级 → [STLink/STLINKV2-1](<./STLink/STLINKV2-1/readme.md>)
- **CMSIS-DAP**：直接烧录 Keil 工程生成的固件 → [DAPLink/wired/STM23F103x](<./DAPLink/wired/STM23F103x/readme.md>)


---

## 所需工具

### 硬件

- SWD 编程器（任何可用的调试器均可）
- 烙铁 + 焊锡（手焊，推荐刀头烙铁）
- 万用表（排查焊接问题）

### 软件

| 工具 | 用途 |
|------|------|
| [J-Link Commander](https://www.segger.com/downloads/jlink/) | 用于符合厂商许可的设备 |
| [ST-LINK Utility / STM32CubeProgrammer](https://www.st.com) | ST-LINK 固件刷写 |
| [Altium Designer / KiCad](https://www.kicad.org) | 查看/编辑 PCB 工程 |
| [Keil MDK](https://www.keil.com) | 编译 CMSIS-DAP 源码 |
| [MounRiver Studio](http://www.mounriver.com/) | 编译 CH32 系列源码（无线 DAPLink、CH570 等） |
| [FT_Prog](https://ftdichip.com/utilities/) | FTDI 芯片配置烧录（MiniWiggler、FTDI JTAG） |
| [Sigrok PulseView](https://sigrok.org/wiki/PulseView) | 逻辑分析仪上位机 |
| [OpenOCD](https://openocd.org) | 通用调试器工具链 |

---

## 注意事项

### 来源、许可与商标

JLink 分类保留硬件参考资料和官方文档链接，不分发 J-Link 软件、固件、提取工具或绕过授权的方法。其他子项目的内容应分别按其来源和许可核查。

原作者署名和已有许可继续适用。没有明确许可证的文件不自动获得使用或再分发授权，请向相应权利人核实。

本项目与 SEGGER、STMicroelectronics 无隶属或背书关系。J-Link、ST-LINK、Arm、CMSIS 等名称或商标属于各自权利人。厂商软件请从官方渠道获取，并遵守对应许可。

### 其他说明

- STM32F103C8T6 有 64KB 和 128KB Flash 两个版本，部分固件可能要求 128KB 版本
- 焊接 0402 封装元件需要一定焊接经验，建议使用刀头烙铁
- 如果遇到识别问题，先检查焊接和供电，再检查 SWD 连接

---

## 贡献

欢迎提交 Issue 或 Pull Request。

J-Link 相关贡献须注明硬件资料来源和再分发依据。不接受专有固件、厂商软件副本、提取工具、绕过授权的方法或夹带此类内容的压缩包；提交前同时检查压缩包内部文件与截图。

- 发现 bug 或问题 → 提交 [Issue](https://github.com/konosubakonoakua/FPGA_MCU_Debugger_Collections/issues)
- 想要完善未完成的项目 → 联系作者或提交 PR

---

## 相关链接

- [J-Link 官方](https://www.segger.com)
- [ST-LINK 官方](https://www.st.com)
- [CMSIS-DAP 规范](https://arm-software.github.io/CMSIS_5/DAP/html/index.html)
- [DAPLink 官方](https://github.com/ARMmbed/DAPLink)
- [BlackMagic Probe 官方](https://black-magic.org)
- [OpenOCD](https://openocd.org)
- [沁恒 WCH](https://www.wch.cn)
- [Sigrok](https://sigrok.org)
