# 黑苹果 OpenCore配置 for ASUS PRIME z390-A 9700K 

## 更新日志
- 12月14日 opencore 升级到 0.6.4 正式版
- 08月04日 opencore 升级到 0.6.0 正式版 

## 硬件配置
- 主板：华硕 PRIME Z390-A [京东地址](https://item.jd.com/100000542145.html)
- CPU：i7-9700k @ 3.6GHz
- 显卡：华硕（ASUS）ROG-STRIX-RX5700XT-O8G-GAMING [京东地址](https://item.jd.com/100004478313.html)
- 内存：美商海盗船(USCORSAIR)DDR4 3200 16GB [京东地址](https://item.jd.com/7706381.html)
- 硬盘：西部数据黑盘 SN750 500G

## BIOS设置（重要）
#### disable
- Fast Boot(快速启动)
- CFG Lock(CFG 锁)
- VT-d
- CSM(兼容性支持模块)
#### enable
- VT-x 
- Above 4G decoding(大于 4G 地址空间解码)
- Hyper Threading(处理器超线程)
- Execute Disable Bit(执行禁止位)
- EHCI/XHCI Hand-off(接手 EHCI/XHCI 控制)
- OS type: other types(操作系统类型: 其他)

## Kexts 版本 8月3日编译 
[参考地址](http://bbs.pcbeta.com/viewthread-1866083-1-1.html)
- AppleALC          1.5.5
- IntelMausi        
- Lilu              1.4.8
- SMCProcessor       
- SMCSuperIO
- USBInjectAll      
- USBPorts
- USBPower
- VirtualSMC        1.1.9
- WhateverGreen     1.4.5

## 软件说明
- 操作系统版本：macOS Catalina 10.15.5 & macOS Big Sur 11.0(beta4)
- OpenCore 版本：0.6.0(正式版)
- UHD630：正常。DeviceProperties -> Add -> `PciRoot(0x0)/Pci(0x2,0x0)` -> `AAPL,ig-platform-id`注入ID `0300983E`。
- 5700XT：驱动W5700x
- 有线网卡：正常。使用了`kexts/IntelMausi.kext`

## 其他
- [OpenCore 实时编译地址](https://github.com/williambj1/OpenCore-Factory/releases)
- [Kexts 下载地址](https://gitee.com/evu/Easy-Kexts)
- [xjn 大佬的博客](https://blog.xjn819.com/?p=543)

## 升级 Big Sur 后 5700xt黑屏
- [远景解决方案 
进BIOS 关掉串口，serial port.  Off /
进BIOS把Super I/O关闭](http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1863274&highlight=5700%2B%BA%DA%C6%C1)
