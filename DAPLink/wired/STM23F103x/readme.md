# CMSIS-DAP / DAPLink（STM32F103）

**中文** | [English](./readme_en.md)

基于 STM32F103C8T6 的有线 CMSIS-DAP 调试器，含完整 Keil 工程源码与两版 Altium PCB 工程；另附 ARM-Mbed DAPLink 的 Altium 硬件工程（固件待补）。

> 文件夹名 `STM23F103x` 为历史拼写，实际芯片为 STM32F103 系列。

## CMSIS-DAP 规格

| 项目 | 详情 |
|------|------|
| **MCU** | STM32F103C8T6 (Cortex-M3) |
| **接口** | SWD + SWO + VCP (虚拟串口 CDC) |
| **亮点** | 两个版本（金手指版 / micro-USB 版），完整 Keil 工程源码 |

## 资料清单

| 文件 | 说明 |
|------|------|
| `STM32F103C8T6_CMSIS-DAP_SWO-master.7z` | 完整 Keil MDK 工程源码 |
| `金手指板CMSISDAP.pdf` | 金手指版原理图 |
| [电路/CMSIS-DAP_T8U6_PCB_Project/](<./电路/CMSIS-DAP_T8U6_PCB_Project/readme.md>) | Altium 工程（T8U6 版），含 `Sheet1.pdf` 原理图 |
| [电路/CMSIS_DAP_PCB_Project/](<./电路/CMSIS_DAP_PCB_Project/readme.md>) | Altium 工程，含 DIY 教程 PDF |
| `电路/CMSIS_DAP_PCB_Project/CMSIS DAP DIY Tutorial (Chinese).pdf` | 中文 DIY 教程 |

### ARM-Mbed DAPLink 硬件工程（未完成）

| 文件 | 说明 |
|------|------|
| `DAPlink_STM32F103-v1.0.0.PrjPcb/` | Altium Designer 工程 |
| `DAPlink_STM32F103-v1.0.0.PrjPcb/DAPlink_STM32F103-v1.0.0.SchDoc` | 原理图 |
| `DAPlink_STM32F103-v1.0.0.PrjPcb/daplink.pdf` | 原理图 / PCB 导出 PDF |
| [DAPLink使用手册.pdf](<./DAPlink_STM32F103-v1.0.0.PrjPcb/DAPLink使用手册.pdf>) | 中文使用手册 |

> DAPLink 固件（bootloader + application）尚未整理上传，欢迎贡献。目标功能：SWD + VCP + 虚拟 U 盘（拖拽烧录）。

## ⚠️ 注意事项

- Keil 设置中**必须勾选 SWJ**，否则报 RDDI-ERROR。
- 程序有所修改：使用了 **PB5 (JNRST) 作为 SWDIO**，与标准引脚不同。
- PCB 请自己画（仓库内工程可作参考）。

## 效果图

Keil 识别效果：

![Keil效果图.png](Keil效果图.png)

实物图：

![](实物1.jpg)

![](实物2.jpg)

## 相关链接

- [DAPLink 官方仓库](https://github.com/ARMmbed/DAPLink)
- [CMSIS-DAP 规范](https://arm-software.github.io/CMSIS_5/DAP/html/index.html)
