# DAPLink / CMSIS-DAP

**中文** | [English](./readme_en.md)

基于 ARM CMSIS-DAP 协议的调试器合集，分**有线**与**无线**两大类。

## 分类

| 分类 | 子项目 | 状态 |
|------|--------|------|
| [Wireless（无线）](<./Wireless/readme.md>) | [ch32v208](<./Wireless/ch32v208/readme.md>) ✅推荐 / [ch32v307](<./Wireless/ch32v307/readme.md>) / [esp32s3](<./Wireless/esp32s3/readme.md>) | 🔗 开源项目链接 + 说明 |
| [wired（有线）](<./wired/readme.md>) | [STM23F103x](<./wired/STM23F103x/readme.md>) / [CH552](<./wired/CH552/readme.md>) / [cmsis_dap_tcp_esp32](<./wired/cmsis_dap_tcp_esp32/readme.md>) | ✅ STM32F103 版完整 |

## 快速选择

- 要**无线调试** → [ch32v208](<./Wireless/ch32v208/readme.md>)（最新设计，推荐）
- 要**自己打板的有线 CMSIS-DAP** → [STM23F103x](<./wired/STM23F103x/readme.md>)（Keil 源码 + Altium 工程齐全）
- 要**网络远程调试** → [cmsis_dap_tcp_esp32](<./wired/cmsis_dap_tcp_esp32/readme.md>)

## 相关链接

- [DAPLink 官方仓库](https://github.com/ARMmbed/DAPLink)
- [CMSIS-DAP 规范](https://arm-software.github.io/CMSIS_5/DAP/html/index.html)
