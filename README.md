# BT_HCI_Firmware
The guide to how to create a hci control 
## 简介

这个仓库存放的是一些如何制作一个蓝牙dongle的固件，保存方便其他人后续学习使用。
主要是把一些蓝牙芯片模拟成一个蓝牙dongle，用来跑一些host的协议栈，或者做一些小demo。

目前主要接口有
HCI_UART (默认H4协议)
HCI_USB(H2)
HCI_UART_H5 (这个暂时没有合适的硬件）
