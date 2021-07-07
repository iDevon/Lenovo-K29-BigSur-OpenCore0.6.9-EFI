# Lenovo-K29-Big-Sur-opencore0.69-EFI
Lenovo K29 Big Sur opencore0.69 EFI

可使用设备及功能：网卡、无线、蓝牙、触控板、摄像头、读卡器、CPU睿频、隔空投送、合盖睡眠、唤醒、投屏、亮度调整、音量调整

K29声卡ALC269 仿冒ID为28

亮度+【Pause】  亮度-【FN+Delete】

音量+【FN+Right】 音量-【FN+Left】

不可用：指纹、风扇转速不显示

CPU为i7-3630QM 非同款CPU请勿加载ACPI/ssdt.aml 

CPU睿频经CPUFriend工具生成ACPI/SSDT_data.aml 不知道为什么CPUFriend无法加载所以才用此方式实现睿频。

EFI修改来源“@黑果小兵 镜像”

目前指纹和风扇转速无法使用，

多次修改DSDT里面的H-EC都不能显示（当然也不能控制转速），所以长时间玩游戏会有些热，不会出现死机等其它故障
