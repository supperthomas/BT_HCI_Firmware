# ESP32

## 如何烧入

下载FLASH TOOL  链接：

https://www.espressif.com/zh-hans/support/download/other-tools

FLASH 烧入参考参数

```
--flash_mode dio --flash_freq 40m --flash_size 2MB
0x1000 bootloader/bootloader.bin
0x10000 controller_hci_uart.bin
0x8000 partition_table/partition-table.bin
```

## 如何制作

IDF 生成工程

![image-20221123211216874](C:\Users\thomas\AppData\Roaming\Typora\typora-user-images\image-20221123211216874.png)



## 如何使用

 TX 5, RX 18, CTS 23, RTS 19  

接USB 转TTL ，波特率921600

输入命令`01 01 10 00` 有回复

