# Wireless DAPLink (CH32V307 + SX1281)

[中文](./readme.md) | **English**

> Open-source project: [dap_hs_wl_v0-4](https://oshwhub.com/ylj2000/dap_hs_wl_v0-4) (by ylj2000, on oshwhub)

DIY wireless debugger based on a CH32V307RCT6 MCU and an SX1281 radio module. Total cost under 100 RMB, with performance rivaling commercial wireless debuggers priced at 300+ RMB.

> 💡 For the newer design, see [ch32v208](../ch32v208/readme_en.md) (the recommended version in this repository).

## Background

When debugging targets that move or are somewhat dangerous (robots, power supplies, etc.), you want your computer far away. Long USB cables are clumsy and limited in length; wireless debuggers on the market vary wildly — many are slow and unstable, and the good ones are expensive (300+ RMB). This project iterated through several revisions to arrive at a practical DIY wireless debugger.

## Specifications

| Item | Details |
|------|---------|
| **MCU** | CH32V307RCT6 (RISC-V) |
| **Radio** | SX1281 wireless module |
| **Interfaces** | SWD + JTAG + Virtual COM Port (VCP) |
| **Reset** | Hardware reset + software reset |
| **Cost** | Under 100 RMB total |
| **Driver** | Driver-free, plug-and-play on Win10 and above |

## Usage

A wireless debugger set consists of a transmitter (Host) and a receiver (Slave); both ends are identical in hardware and firmware:

- Pairing, mode switching, and parameter tuning via button or host-side utility.
- Debugs ARM MCUs (STM32, GD32, etc.).
- Besides wireless mode, a wired (USB) mode is available for temporary use in RF-hostile environments, with higher performance than wireless.

## Status LED

| Color | Mode |
|-------|------|
| Red | Wired mode (USB) |
| Blue | Wireless transmitter (Host) |
| Green | Wireless receiver (Slave) |

| Pattern | Meaning |
|---------|---------|
| Breathing | Connected, normal |
| Slow blink | Other end not ready (unpowered or unpaired) |
| Fast blink | Download/debug in progress or VCP data flowing |

![](https://image.lceda.cn/pullimage/VJIKQlAjZ5qBLdmV7z70NC1mxENjSsbCOFpdhgC2.jpeg)
