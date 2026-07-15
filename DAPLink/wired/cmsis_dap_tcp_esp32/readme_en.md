# CMSIS-DAP over TCP (ESP32)

[中文](./readme.md) | **English**

> Open-source project: [bkuschak/cmsis_dap_tcp_esp32](https://github.com/bkuschak/cmsis_dap_tcp_esp32)

OpenOCD supports the CMSIS-DAP protocol to communicate with a JTAG / SWD programmer — typically a local programmer over USB. With the OpenOCD `cmsis_dap_tcp` backend, the CMSIS-DAP protocol can now run over **TCP/IP** instead of USB, allowing OpenOCD to connect to a remote programmer over the network.

This project provides the remote-side implementation of the `cmsis_dap_tcp` protocol, using an ESP32 as the remote programmer:

- A cheap ESP32 board programs and debugs an ARM microcontroller target
- Both JTAG and the two-wire SWD interface are supported
- OpenOCD connects to the ESP32 via TCP/IP over WiFi, enabling remote flashing and debugging

![](https://github.com/bkuschak/cmsis_dap_tcp_esp32/raw/main/img/cmsis_dap_tcp_diagram.svg)
