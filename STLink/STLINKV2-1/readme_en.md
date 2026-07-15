# ST-LINK V2-1 (V2 Mod)

[中文](./readme.md) | **English**

Modify ST-LINK V2 hardware into an ST-LINK V2-1, gaining virtual COM port + virtual USB drive functionality.

## Specifications

| Item | Details |
|------|---------|
| **Hardware** | Modified ST-LINK V2 hardware (STM32F103C8T6) |
| **Interfaces** | SWD + VCP (virtual COM port) + virtual USB drive |

## File manifest

| File | Description |
|------|-------------|
| `STLinkV2.J28.M18_stlinkv2.1_bootloader.rar` | V2-1 bootloader |
| `STLinkV2.J28.M18_解除读保护.bin` | Firmware with read protection removed |
| `STLINKV2 Firmware/STLinkV2.J27.S6.bin` | ST-LINK V2 firmware backup |
| `st-decrypt-master/` | Java ST-LINK firmware decrypt/encrypt tool (third-party, see its [README](./st-decrypt-master/README.md)) |
| [option_bytes_config.png](./option_bytes_config.png) | Option bytes configuration reference |

## Build steps (extremely simple)

1. Cut (however you like) the traces between the SWIM / RST ports and the PCB
2. Jumper-wire the STM32's PA2 and PA3 to SWIM and RST
3. Connect another ST-LINK via SWD to the ST-LINK being modified
4. Use ST-LINK Utility to unlock read protection and erase the chip
5. Flash the bootloader bin file
6. Use ST-LINK Utility's Firmware Update to upgrade automatically
7. Done — enjoy your ST-LINK V2-1 🎉

## st-decrypt usage

```
java -jar st_decrypt.jar --key "best performance" -i firmware.bin -o firmware_decrypted.bin
```

## Success screenshots

![](keil识别为V2-1.png)

![](U盘.png)

![](虚拟串口.png)

![](completed1.jpg)

![](completed2.jpg)
