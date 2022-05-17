# 黑苹果 OpenCore配置 for ASUS PRIME z390-A 9700K 

## 更新日志
- 22年04月01日 opencore 升级到 0.7.9 正式版 
- 21年12月08日 opencore 升级到 0.7.6 正式版 
- 21年08月07日 opencore 升级到 0.7.2 正式版 
- 21年07月28日 opencore 升级到 0.7.1 正式版 
- 21年05月06日 opencore 升级到 0.6.9 正式版 
- 21年04月30日 opencore 升级到 0.6.8 正式版 
- 21年03月02日 opencore 升级到 0.6.7 正式版 
- 21年02月18日 opencore 升级到 0.6.6 正式版 
- 21年01月06日 opencore 升级到 0.6.5 正式版
- 20年12月14日 opencore 升级到 0.6.4 正式版
- 20年08月04日 opencore 升级到 0.6.0 正式版 

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
- [AppleALC](https://github.com/acidanthera/AppleALC/releases)          1.6.2
- [IntelMausi](https://github.com/acidanthera/IntelMausi/releases)        1.0.7
- [Lilu](https://github.com/acidanthera/Lilu/releases)              1.5.4
- SMCProcessor      - VirtualSMC
- SMCSuperIO        - VirtualSMC
- [USBInjectAll](https://github.com/Sniki/OS-X-USB-Inject-All/releases)      0.7.5  已删除
- USBPorts    定制USB 其他机型会不匹配
- [VirtualSMC](https://github.com/acidanthera/virtualsmc/releases)        1.2.5
- [WhateverGreen](https://github.com/acidanthera/whatevergreen/releases)     1.5.1
- [NVMeFix](https://github.com/acidanthera/NVMeFix/releases)    1.0.9

## 软件说明
- 操作系统版本：macOS Catalina 10.15.5 & macOS Big Sur 11.0(beta4)
- OpenCore 版本：0.6.0(正式版)
- UHD630：正常。DeviceProperties -> Add -> `PciRoot(0x0)/Pci(0x2,0x0)` -> `AAPL,ig-platform-id`注入ID `0300983E`。
- 5700XT：驱动W5700x
- 有线网卡：正常。使用了`kexts/IntelMausi.kext`
- 定制USB PS 11.3 后的Mac os 需要定制USB 才能正常使用USB
- 蓝牙免驱设备定制在USB_E12的端口上 并设置内建设备(Internal)

## 其他
- [OpenCore 实时编译地址](https://github.com/williambj1/OpenCore-Factory/releases)
- [Kexts 下载地址](https://gitee.com/evu/Easy-Kexts)
- [xjn 大佬的博客](https://blog.xjn819.com/?p=543)
- [主题资源文件 OcBinaryData](https://github.com/acidanthera/OcBinaryData)
- [文档](https://dortania.github.io/OpenCore-Post-Install/)
- [OC-little](https://github.com/daliansky/OC-little) config配置详解
- [ACPI定制USB端口](https://github.com/daliansky/OC-little/blob/master/15-ACPI%E5%AE%9A%E5%88%B6USB%E7%AB%AF%E5%8F%A3/README.md)
- [Intel无线网卡](
https://github.com/OpenIntelWireless/itlwm/releases)
- [关闭n卡 ](https://dortania.github.io/Getting-Started-With-ACPI/Desktops/desktop-disable.html#finding-the-acpi-path-of-the-gpu)
- [ACPI定制](https://dortania.github.io/Getting-Started-With-ACPI/)
- [OpenCore 定制](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html)
## 升级 Big Sur 后 5700xt黑屏
- [远景解决方案 
进BIOS 关掉串口，serial port.  Off /
进BIOS把Super I/O关闭](http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1863274&highlight=5700%2B%BA%DA%C6%C1)

## 虚拟化设置
在bios里把VT-D打开，在oc里把DisableIoMapper改为yes

## Mac OS 下载地址
-  [macOS Big Sur](https://apps.apple.com/cn/app/macos-big-sur/id1526878132?ls=1&mt=12)
-  [macOS Catalina](https://apps.apple.com/cn/app/macos-catalina/id1466841314?ls=1&mt=12)
-  [macOS Mojave](https://apps.apple.com/cn/app/macos-mojave/id1398502828?ls=1&mt=12)
-  [macOS High Sierra](https://apps.apple.com/cn/app/macos-high-sierra/id1246284741?ls=1&mt=12)
-  [macOS Monterey](https://apps.apple.com/cn/app/macos-monterey/id1576738294?mt=12)

## 制作启动盘
> sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolumeName