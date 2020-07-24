# 黑苹果 OpenCore配置 for ASUS PRIME z390-A 9700K 

## 更新日志
- 7月24日 opencore 升级到 2020-07-24

## 硬件配置
- 主板：华硕 PRIME Z390-A [京东地址](https://item.jd.com/100000542145.html)
- CPU：i7-9700k @ 5.2GHz
- 显卡：华硕（ASUS）ROG-STRIX-RX5700XT-O8G-GAMING [京东地址](https://item.jd.com/100004478313.html)
- 内存：美商海盗船(USCORSAIR)DDR4 3200 16GB [京东地址](https://item.jd.com/7706381.html)
- 硬盘：西部数据黑盘 SN750 500G

## BIOS设置（重要）
略

## 软件说明
- 操作系统版本：macOS Catalina 10.15.5 & macOS Big Sur 11.0
- OpenCore 版本：0.6.0(2020.07.10当天编译)
- UHD630：正常。DeviceProperties -> Add -> `PciRoot(0x0)/Pci(0x2,0x0)` -> `AAPL,ig-platform-id`注入ID `0300983E`。
- 5700XT：驱动W5700x
- 有线网卡：正常。使用了`kexts/IntelMausi.kext`

## 其他
- [OpenCore 实时编译地址](https://github.com/williambj1/OpenCore-Factory/releases)
- [Kexts 下载地址](https://gitee.com/evu/Easy-Kexts)
