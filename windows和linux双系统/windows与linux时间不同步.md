1.修改Windows的时间设定：
让`Windows`把硬件时间当作 UTC  
开始->运行->CMD，打开命令行程序(Vista则要以管理员方式打开命令行程序方可有权限访问注册表)，在命令行中输入下面命令并回车
```cmd
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```
2.修改`Linux`时间设定，将BIOS时间作为本地时间：
使用`timdatectl`命令设置：
```shell
$ timedatectl status | grep local
#将硬件时间设置为 localtime:
$ timedatectl set-local-rtc true
#硬件时间设置成 UTC（恢复默认设置）：
$ timedatectl set-local-rtc false
```