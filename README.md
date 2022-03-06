# Lenovo-K29-Big-Sur-opencore0.69-EFI
Lenovo K29 Big Sur opencore0.69 EFI

可使用设备及功能：网卡、无线、蓝牙、触控板、摄像头、读卡器、CPU睿频、隔空投送、合盖睡眠、唤醒、投屏、亮度调整、音量调整

K29声卡ALC269 仿冒ID为28

亮度+【Pause】  亮度-【FN+Delete】

音量+【FN+Right】 音量-【FN+Left】

风扇转速显示正常
在DSDT中H-EC上面添加SMCD
```
Device (SMCD)
                {
                    Name (_HID, "FAN00000")  // _HID: Hardware ID
                    Name (_CID, "monitor")  // _CID: Compatible ID
                    Name (TACH, Package (0x02)
                    {
                        "System Fan", 
                        "FAN0"
                    })
                    Method (FAN0, 0, NotSerialized)
                    {
                        Local0 = (^^H_EC.FSP1 << 0x08)
                        Local0 |= ^^H_EC.FSPD /* \_SB_.PCI0.LPCB.H_EC.FSPD */
                        Return (Local0)
                    }
                }
```
并在DeviceProperties内建 风扇转速显示正常
![截屏2022-03-06 上午11 36 38](https://user-images.githubusercontent.com/86851841/156908140-7111beb5-dfd0-43e7-9fbb-0f80ae1e7e2e.png)

![截屏2022-03-06 上午11 34 33](https://user-images.githubusercontent.com/86851841/156908108-6bffdabd-d46b-4a33-aae6-2169b5b258f2.png)

不可用：指纹

CPU为i7-3630QM 非同款CPU请勿加载ACPI/ssdt.aml 

CPU睿频经CPUFriend工具生成ACPI/SSDT_data.aml 不知道为什么CPUFriend无法加载所以才用此方式实现睿频。


