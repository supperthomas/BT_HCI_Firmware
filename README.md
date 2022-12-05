# BT_HCI_Firmware
The guide to how to create a hci control 
## 简介

这个仓库存放的是一些如何制作一个蓝牙dongle的固件，保存方便其他人后续学习使用。
主要是把一些蓝牙芯片模拟成一个蓝牙dongle，用来跑一些host的协议栈，或者做一些小demo。

目前主要接口有
HCI_UART (默认H4协议)
HCI_USB(H2)
HCI_UART_H5 (这个暂时没有合适的硬件）

## ESP32

ESP32 没有USB

只有HCI_UART接口：

烧入方法，见[readme](01_ESP/01_ESP32/readme.md)

需要注意的是：通常用的接电脑的USB不是HCI_UART口

需要另外接线接USB转TTL的口到电脑。

## Nordic

### nrf52840 DK

nrf52840 是带USB的

#### HCI_USB

用固件，直接托到JLINK 枚举的U盘即可，这个需要另外一个USB线接到DK的另外一个USB口

 [HCI_USB_BLE_ADAPTER_nrf52840_no_dfu.hex](02_Nordic\HCI_USB\HCI_USB_BLE_ADAPTER_nrf52840_no_dfu.hex) 

#### HCI_UART

 [hci_uart_nrf52840dk_115200.hex](02_Nordic\HCI_UART\hci_uart_nrf52840dk_115200.hex) 

波特率是115200 ，直接插上JLINK 就可以进行通信，用的是JLINK里面的CDC

制作方法：zephyr hci_uart

### nrf52840 dongle

这个是带bootloader的，

bootloader用固件 [pca10059_bootloader_mbr_v1.0.1.hex](02_Nordic\pca10059_bootloader_mbr_v1.0.1.hex) 

app用固件  [hci_usb_nrf52840dongle_dfu_app.hex](02_Nordic\HCI_USB\hci_usb_nrf52840dongle_dfu_app.hex) 

之后模拟的是HCI_USB 的dongle设备，电脑可以蓝牙适配器模拟

USB接口

制作方法：出厂自带的固件

### nrf52832 DK

nrf52832 没有USB模块

所以只能是HCI_UART 模块

 [hci_uart_nrf52832dk_115200.hex](02_Nordic\HCI_UART\hci_uart_nrf52832dk_115200.hex) 
使用方法：

直接拖到JLINK枚举的设备中

制作方法：zephyr HCI_UART



