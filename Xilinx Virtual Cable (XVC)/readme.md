# Xilinx Virtual Cable (XVC)

**中文** | [English](./readme_en.md)

Xilinx Virtual Cable (XVC) 是通过网络进行 Xilinx FPGA JTAG 调试的协议。以下为相关开源项目。

## [xvc-pico](https://github.com/kholia/xvc-pico)

基于 Raspberry Pi Pico 的 Xilinx Virtual Cable：

- 可将 Pico（及 Pico 2）用作 JTAG 适配器，为 Xilinx FPGA 编程

![](https://github.com/kholia/xvc-pico/raw/ng/pinout.png)

## [jtag-remote-server](https://github.com/jiegec/jtag-remote-server)

远程芯片调试工具：

- 依赖 libftdi 与 FTDI 芯片通信
- 暴露多种协议用于远程调试
