# Wireless DAPLink (CH32V208 / CH32V305)

[中文](./readme.md) | **English**

> Open-source project: [dap_v208_v305_open](https://oshwhub.com/ylj2000/dap_v208_v305_open) (by ylj2000, on oshwhub)

Next-generation wireless DAPLink debugger — **the recommended wireless DAPLink option in this repository**.

## Specifications

| Item | Details |
|------|---------|
| **MCU (FS version)** | CH32V208, BOM cost ~10 RMB/pcs |
| **MCU (HS version)** | CH32V208 + CH32V305, BOM cost ~18 RMB/pcs |
| **Interfaces** | SWD + JTAG + Virtual COM Port (VCP) |
| **Reset** | Hardware reset + software reset |
| **Wireless range** | 100m+ measured with on-board antenna at 2M air rate; 1km+ expected with external antenna or lower air rate |
| **Driver** | Driver-free, plug-and-play on Win10 and above |

## Version notes

- FS and HS versions share **exactly the same PCB** — only the soldered components differ.
- A Mini FS version the size of a mouse dongle also exists, with the same performance as FS.
- The HS version mainly gives a 3×+ boost where the DAP V1 protocol is mandatory (old MDK versions, Ozone, etc.). Using HS on the host side only and FS on the slave side performs identically to dual HS.
- For the FS version, MDK ≥ 5.29 / IAR ≥ 8.32 recommended, to avoid poor performance from USB FS + DAP V1.
- Both wired and wireless performance far exceed the two earlier designs ([ch32v307](../ch32v307/readme_en.md), [esp32s3](../esp32s3/readme_en.md)): wired beats J-Link V9, wireless beats ST-LINK V2, with low latency for a smooth debug experience.

## Usage

A wireless debugger set consists of a master and a slave; both ends are identical in hardware and firmware:

- Plug into USB to enumerate as a USB drive for configuration; pairing and mode switching can also be done with the button.
- Debugs ARM MCUs (STM32, GD32, etc.); also supports wireless download to ESP32.
- Besides wireless mode, a wired (USB) mode is available for RF-hostile environments, with even higher performance.
- Uses a custom frequency-hopping algorithm — stable and fast.

## Status LED

| Color | Mode |
|-------|------|
| Red | Wired mode (USB) |
| Blue | Wireless master |
| Green | Wireless slave |

| Pattern | Meaning |
|---------|---------|
| Breathing | Connected, normal |
| Slow blink | Other end not ready (unpowered or unpaired) |
| Fast blink | Data transfer in progress |

![](https://image.lceda.cn/oshwhub/pullImage/7b74225e8ac249efbd5b05b7bf4784e9.jpg)
