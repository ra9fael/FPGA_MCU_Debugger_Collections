# CH570 无线串口

**中文** | [English](./readme_en.md)

> 开源项目：[ch570q-uart1](https://oshwhub.com/fikasgroup/ch570q-uart1)（作者 fikasgroup，立创开源硬件平台）
>
> 本目录 `CH570-Wireless-2v0.zip` 为设计资料包。

## 项目简介

![](https://image.lceda.cn/oshwhub/pullImage/f7ea1a1f6e5f42ecbac79c3ca6b3ffbb.png)

一款在电脑和 MCU 之间实现无线串口通信的小工具，全双工，兼具 MCU 下载功能。成对使用：一个 Dongle 插电脑，另一个模块连 MCU。两边主控都采用 RISC-V 无线 SoC 芯片 **CH570Q**。

选 CH570 的原因：自带 USB 无线串口例程，且兼容 CH340 驱动程序，代码改起来比较容易。本方案在官方例程基础上又堆了些代码，主要是提升串口性能、增加 MCU 串口无线下载、连接状态指示功能。

为方便制作，Dongle 和模块共用一个 PCB：做 Dongle 时从中间掰断，塞进接收器外壳里；做模块连 MCU 时不用掰，直接焊排针即可。

![](https://image.lceda.cn/pullimage/Nugvw8yp4EqVPRlr1LcsmzRjcV99Gy7xgVai0Mq5.png)

## 工作原理

- **Dongle 端**：USB 虚拟串口与 2.4G 无线的双向透传。CH570 通过 USB 枚举成串口设备，接收电脑发来的串口设置和数据，经 2.4G 发送给对端模块，同时将 2.4G 收到的数据经 USB 传给电脑。
- **模块端**：无线 2.4G 与有线串口的双向透传。CH570 接收 Dongle 端发来的串口参数并配置自身串口，将收到的数据用串口发给 MCU，同时将 MCU 发来的数据用 2.4G 传给 Dongle。

## 使用方法

**如何建立连接？** 支持"一碰连"：Dongle 和模块互相靠近时无线信号增强，超过设定阈值即自动连接。上电后彼此靠近一下就能连上。第一次配对后信息保存，之后上电/掉电重启均自动重连。两端均有 LED：连接成功后常亮，通信时闪烁。

**模块端如何设置串口参数？** 电脑串口软件点击"打开串口"时，串口参数经 USB 发给 Dongle 内的 CH570，再经 2.4G 发给对端模块，模块据此设定串口，实现两侧参数同步。只要电脑端设置 MCU 支持的串口参数，模块即可正常通信。

无线串口工作流程图：

![](https://image.lceda.cn/pullimage/1cb1L9oXt9vOGGgrkdGKlehWILLaz5GpSBYMhWoP.png)
