# CH570 Wireless Serial Port

[中文](./readme.md) | **English**

> Open-source project: [ch570q-uart1](https://oshwhub.com/fikasgroup/ch570q-uart1) (by fikasgroup, on oshwhub)
>
> `CH570-Wireless-2v0.zip` in this folder is the design resource pack.

## Overview

![](https://image.lceda.cn/oshwhub/pullImage/f7ea1a1f6e5f42ecbac79c3ca6b3ffbb.png)

A small tool for wireless UART communication between a PC and an MCU — full duplex, with MCU download capability. Used in pairs: one dongle plugs into the PC, the other module connects to the MCU. Both ends use the RISC-V wireless SoC **CH570Q**.

Why CH570: it ships with a USB wireless-UART example and is compatible with the CH340 driver, making the code easy to adapt. This design builds on the official example, mainly improving UART performance and adding wireless MCU UART download and connection status indication.

For easy fabrication, the dongle and module share one PCB: for a dongle, snap it in the middle and fit it into a receiver shell; for a module, keep it whole and solder pin headers.

![](https://image.lceda.cn/pullimage/Nugvw8yp4EqVPRlr1LcsmzRjcV99Gy7xgVai0Mq5.png)

## How it works

- **Dongle side**: bidirectional bridge between the USB virtual COM port and the 2.4G radio. The CH570 enumerates as a serial device over USB, takes the PC's serial settings and data, sends them over 2.4G to the module, and forwards data received over 2.4G back to the PC via USB.
- **Module side**: bidirectional bridge between the 2.4G radio and the wired UART. The CH570 receives the serial parameters from the dongle, configures its own UART accordingly, sends received data to the MCU over UART, and forwards the MCU's data to the dongle over 2.4G.

## Usage

**How do the ends pair?** "Tap-to-connect": as the dongle and module get close, the received signal strengthens; once above the threshold, they auto-connect. Just bring them close after power-up. Pairing info is saved after the first time, and both ends auto-reconnect on subsequent power cycles. Both have LEDs: solid when connected, blinking during traffic.

**How does the module get its serial parameters?** When you click "open port" in your PC serial software, the parameters go over USB to the CH570 in the dongle, then over 2.4G to the module, which configures its UART to match — both sides stay in sync. As long as the PC sets parameters the MCU supports, communication just works.

Wireless UART workflow:

![](https://image.lceda.cn/pullimage/1cb1L9oXt9vOGGgrkdGKlehWILLaz5GpSBYMhWoP.png)
