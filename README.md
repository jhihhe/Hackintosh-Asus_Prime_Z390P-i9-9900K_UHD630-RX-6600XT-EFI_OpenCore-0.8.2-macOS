# *Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630&6600XT-EFI_OpenCore-0.8.0 macOS*

# [中文](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.0-macOS/blob/main/README.md)｜[English](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.0-macOS/blob/main/README-EN.md)

# 下载点击[releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.0-macOS/releases)
仅使用核显请下载IGPU版本或版本号小于220305的版本
# 请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM

![系统信息](https://pic.imgdb.cn/item/623451515baa1a80ab1e5782.png)
![System Information 2](https://pic.imgdb.cn/item/623453995baa1a80ab205c96.png)
### 配置
1. 主板: ASUS PRIME Z390-P （BIOS Version 3006 请点击这里[下载BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) ）
1. CPU: Intel® Core™ i9-9900K Processor
1. 核显: Intel® UHD Graphics 630(仅使用核显请下载IGPU版本或版本号小于220305的版本)
1. 显卡: AMD Radeon RX 6600 XT
1. 板载网卡: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/蓝牙: BCM943602CS（BT4.2）
1. 声卡: Realtek® ALC 887 8-Channel High Definition Audio
1. 固态硬盘: 西数SN750 500GB（开启TRIM）
![硬盘信息](https://tva1.sinaimg.cn/large/cec1774cly8h057sy9inrj21860u0tcy.jpg)

### BIOS设置
1. 高级-CPU设置--Intel(VMX) Virtualization Technology -enable
1. 高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-1024M，RC6-auto
1. 高级-USB Configuration--XHCI Hand-off -enable
1. 高级-内置设备-Serial Port Configuration-Serial Port -off
1. 启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable
1. 设置模式-高级模式

# **可适用操作系统版本：macOS Catalina 10.15.1～Big Sur 11.6.5/支持macOS Monterey 12.3**
1. OpenCore版本：0.8.0（内含主题如下图） 
![主题](https://i.loli.net/2021/09/11/t4FBZPeHkwdufiG.png)
![主题](https://i.loli.net/2021/07/31/uFHJD2BMazqmTcA.png)
1. CPU变频：工作正常。 
![CPU](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg)
![内存](https://tva2.sinaimg.cn/large/cec1774cly8h057svhmylj21860u0n0u.jpg)
1. UHD630：工作正常，VRAM动态，最大值：4095 MB，开启HIDPI，开启H.264&HEVC硬件解码加速，RX6600XT：工作正常，增加独显AAPL,slot-name参数，加入RadeonSensor.kext&SMCRadeonGPU.kext，以正常显示独立显卡温度
![显卡](https://tva1.sinaimg.cn/large/cec1774cly8h057srbj3nj21860u0tc0.jpg)
![显卡2](https://tva1.sinaimg.cn/large/cec1774cly8h057n6odtqj20lq0tgq5h.jpg)
![硬件解码加速：H.264&HEVC解码](https://tva3.sinaimg.cn/large/cec1774cly8gzz45wjjlrj21880u0tc6.jpg)
1. 3.5mm声音：工作正常
![声卡](https://tva3.sinaimg.cn/large/cec1774cly8h057stfz6fj21860u0gov.jpg)
1. USB：工作正常，Big Sur 11.3版本后，如USB加载不正常，需自行定制usb，或取消加载USBport.kext，将XhciPortLimit值变更为true 
![USB](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1ee.png)
1. 有线网卡：工作正常，使用了RealtekRTL8111.kext 
![有线网卡](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1f6.png)
1. 无线网卡：工作正常 
![Wi-Fi](https://pic.imgdb.cn/item/62280dd25baa1a80abdfa953.png)
1. 睡眠唤醒：工作正常 
![睡眠2](https://tva2.sinaimg.cn/large/cec1774cly8h057snf0lzj21860u0wh5.jpg)
![睡眠](https://tva1.sinaimg.cn/large/cec1774cly8h057wpxhe1j212p0u0410.jpg)
1. 关机开机：工作正常
1. iCloud & App Store & iMessage & FaceTime：正常
1. AirDrop & HandOff & Continuity：正常。
![蓝牙](https://pic.imgdb.cn/item/62280dcf5baa1a80abdfa682.png)

### Tips：

1. 机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。
1. 该config默认为无verbose模式。如需启用verbose模式，config.plist需要修改以下一项：NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v。
1. 该config启动盘策略 ScanPolicy 值设置为0。可引导Windows或Other OS（Linux、Unix）如需指定搜索分区类型，可参考OC配置手册。

# 鸣谢 
# 采用了igarashikenshin的README.md编辑格式，如果需其他版本可点击大佬链接查看
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
