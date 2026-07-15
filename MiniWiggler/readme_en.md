# Infineon MiniWiggler

[中文](./readme.md) | **English**

> Open-source project: [3-in-1 programmer](https://oshwhub.com/xljxlj/san-he-yi-xia-zai-qi) (by xljxlj, on oshwhub)

Clone of the Infineon MiniWiggler 3-in-1 programmer; schematic based on the on-board programmer of Infineon's official dev boards.

> Commercial use allowed (author's name on the board and the open-source link must be kept); derivative works permitted.

## Features

- All-PCB construction, assembled with brass standoffs; fits JLC's free-prototyping process (choose 1.0mm thickness for easy cutting)
- Supports **DAP and JTAG download**, plus a separate UART interface
- Over-current protection, ESD protection, external IO voltage supported
- Firmware in the project attachments; flash with **FT_Prog**
- Note: the IDC socket mounts recessed — pins need trimming

## RGB status LED

| Color | State |
|-------|-------|
| Red | Host-controlled power-off / USB not connected / over-current protection / no external power |
| Green | Connected |
| Blue | Debugging |

## Switches

| Switch | Function |
|--------|----------|
| Top-right | Toggle debug-UART pinout between Zhufei / Longqiu core boards |
| Bottom-left #1 | IO voltage: internal 3.3V / external supply |
| Bottom-left #2 | JTAG / DAP download mode (JTAG and DAP use separate connectors) |

## Assembly BOM

| Part | Qty |
|------|-----|
| M2×3mm screws | 4 |
| M2×3 double-pass knurled standoffs | 4 |
| M2×6+3 single-pass knurled standoffs | 4 |

![](https://image.lceda.cn/pullimage/FKw7xieL8kZpJEn0Bx4XGPGpPM7AxSJVodK7cpKl.jpeg)
