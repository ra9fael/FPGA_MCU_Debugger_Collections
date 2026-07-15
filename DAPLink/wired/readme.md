# 有线 DAPLink / CMSIS-DAP 方案

**中文** | [English](./readme_en.md)

基于 CMSIS-DAP 协议的有线调试器方案。

## 子项目

| 子项目 | 主控/方案 | 说明 | 状态 |
|--------|-----------|------|------|
| [STM23F103x](<./STM23F103x/readme.md>) | STM32F103C8T6 | CMSIS-DAP（SWD+SWO+VCP，Keil 源码 + Altium 工程）；含 ARM-Mbed DAPLink 硬件工程 | ✅ 完整（DAPLink 固件待补） |
| [CH552](<./CH552/readme.md>) | CH552 | wagiminator 开源 CMSIS-DAP（SWD+JTAG+VCP） | 🔗 仅链接 |
| [cmsis_dap_tcp_esp32](<./cmsis_dap_tcp_esp32/readme.md>) | ESP32 | CMSIS-DAP over TCP/IP，OpenOCD 网络远程调试 | 🔗 仅链接 |
