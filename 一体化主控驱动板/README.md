#  一体化主控驱动板

面向智能车整机控制的重点综合硬件项目。设计以 Infineon AURIX TC377 为主控，在单板上集成双路无刷电机功率驱动、四路舵机电源、六轴 IMU、双磁编码器、摄像头、屏幕、UART、下载调试与多种人机输入接口，减少板间连接并形成完整的控制与执行硬件平台。



- 使用五页层次化原理图，将系统拆分为 MCU、电源、外设、无刷驱动和舵机电源五个功能域。
- 围绕 SAK-TC377TP 完成核心供电、时钟、复位、启动配置和调试下载接口设计。
- 构建 5 V、3.3 V、摄像头 3.3 V、1.3 V 等多路电源，并加入 TVS、输入保护、开关和电压检测。
- 集成两套 DRV8323HR 栅极驱动与 MOSFET 三相桥，对应两路无刷电机输出。
- 集成 ICM-42688P 六轴 IMU、两路 SPI 磁编码器、摄像头 FPC、屏幕、UART 和拨码/多向开关。
- 布置四路独立舵机供电与 PWM/电源/地接口，降低执行器对主控电源的扰动。
- 完成高集成度 PCB 正反面布局及 3D 装配检查，统筹功率器件、传感器和外部接口的位置关系。

## 系统架构

| 模块 | 主要设计 |
| --- | --- |
| 主控 | Infineon AURIX TC377、晶振、复位、Boot 与下载调试 |
| 电源 | 输入保护、多路 DC-DC/LDO、核心电源、模拟/数字电源与电压监测 |
| 运动控制 | 双路 DRV8323HR + MOSFET 三相桥、两路磁编码器接口 |
| 传感与通信 | ICM-42688P、摄像头、屏幕、UART、多组 SPI |
| 执行器 | 四路舵机 PWM 接口与独立降压供电 |
| 人机输入 | 拨码开关、多向开关、状态/故障指示 |

## 

嘉立创 EDA Pro、Infineon AURIX TC377、DRV8323HR、三相 MOSFET 功率级、ICM-42688P、SPI、UART、FPC、Buck/LDO、电源完整性与 PCB Layout

## 文件说明

- `ProPrj_v1.2release_2026-09-09.epro`：v1.2release 完整 EDA 工程。
- `schematic-mcu.png`：TC377 核心、时钟、复位与下载调试。
- `schematic-power.png`：多路电源、保护、开关与电压检测。
- `schematic-peripherals.png`：编码器、IMU、摄像头、屏幕、UART 与开关接口。
- `schematic-peripherals-with-notes.png`：带完整页框和说明的外设原理图版本。
- `schematic-motor-driver.png`：双路无刷预驱与 MOSFET 功率级。
- `schematic-servo-power.png`：四路舵机供电。
- `pcb-layout-top.png`、`pcb-layout-bottom.png`：PCB 正反面布局。
- `pcb-3d-top.png`、`pcb-3d-bottom.png`：正反面三维装配效果。

