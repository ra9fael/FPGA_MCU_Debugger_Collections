# CMSIS-DAP over TCP（ESP32）

**中文** | [English](./readme_en.md)

> 开源项目：[bkuschak/cmsis_dap_tcp_esp32](https://github.com/bkuschak/cmsis_dap_tcp_esp32)

OpenOCD 支持通过 CMSIS-DAP 协议与 JTAG / SWD 编程器通信，通常是本地 USB 连接。加入 OpenOCD 的 `cmsis_dap_tcp` 后端后，CMSIS-DAP 协议可以通过 **TCP/IP** 而非 USB 运行，使 OpenOCD 能连接网络上的远程编程器。

本项目提供 `cmsis_dap_tcp` 协议的远端实现，用 ESP32 作为远程编程器：

- 用廉价 ESP32 开发板对 ARM 单片机目标进行编程和调试
- 支持 JTAG 和两线 SWD 接口
- OpenOCD 通过 WiFi 上的 TCP/IP 连接 ESP32，实现远程烧录和调试

![](https://github.com/bkuschak/cmsis_dap_tcp_esp32/raw/main/img/cmsis_dap_tcp_diagram.svg)
