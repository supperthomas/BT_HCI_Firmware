# ESP32

## 如何烧入

下载FLASH TOOL  链接：

https://www.espressif.com/zh-hans/support/download/other-tools

FLASH 烧入参考参数

```
--flash_mode dio --flash_freq 80m --flash_size 2MB
0x0 bootloader.bin
0x10000 controller_hci_uart_demo.bin
0x8000 partition-table.bin
```

## 如何制作

IDF 生成工程

选择ESP32C3特定的hci_uart

## 如何使用

TxD 4, RxD 5, RTS 6, CTS 7

接USB 转TTL ，波特率115200

输入命令`01 01 10 00` 有回复

