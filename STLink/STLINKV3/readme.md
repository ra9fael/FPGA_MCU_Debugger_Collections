# ST-LINK V3 制作

**中文** | [English](./readme_en.md)

> **状态：未完成。** 当前仅收录 ST 官方参考设计，固件和自定义 PCB 待补充，欢迎贡献。

## 当前进度

- ST 官方参考设计原理图 (MB1367) 已上传
- 固件和自定义 PCB 尚未整理

## 资料清单

| 文件 | 说明 |
|------|------|
| [MB1367C/mb1367.pdf](./MB1367C/mb1367.pdf) | ST 官方 MB1367 参考设计原理图 |
| `MB1367C/MB1367C.7z` | ST 官方 MB1367C 参考设计工程 |
| [v3 mini/](<./v3 mini/readme.md>) | V3 Mini 开源方案（原理图 + BOM PDF） |

## 硬件规格

ST-LINK V3 是 ST 官方最新一代调试器：

- **MCU**: STM32F723IE (Cortex-M7)
- **接口**: SWD + JTAG + VCP + 桥接功能 (SPI/I2C/CAN/GPIO)
- **最高 SWD 频率**: 24 MHz
- **特色**: 支持 STDC14 连接器和传统 JTAG/SWD 排针

## 待完成

- [ ] 整理并上传固件
- [ ] 设计自定义 PCB
- [ ] 编写制作教程

## 相关链接

- [ST-LINK V3SET 官方页面](https://www.st.com/zh/development-tools/stlink-v3set.html)
- [ST-LINK MB1367 参考设计](https://www.st.com)
