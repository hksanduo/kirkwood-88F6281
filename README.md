# kirkwood-88F6281

## 简介
任子行88F6281的openwrt 19.07 patch源码及配置文件，是source/target/linux/kirkwood目录中的内容
固件命名为"butong",可以自行设定,支持的内核版本为4.14.

## 编译
### menuconfig配置
平台选择kirkwood butong

### kernel_menuconfig配置
在 **Device Drivers** 下选择 **MMC/SD/SDIO**

## uboot配置
uboot配置,从sd卡启动项目,开机默认启动SD卡系统
在命令行上输入
```
setenv bootmmc 'setenv bootargs console=ttyS0,115200 root=/dev/mmcblk0p2 init=/etc/preinit rootfstype=ext4 rw rootwait;mmcinit;mmcinit;fatload mmc 0:1 2000000 kernel;bootm 2000000;'

setenv bootcmd 'run bootmmc'  

saveenv

reset
```
## 注意事项
对于其他采用marvell 88F6281芯片的路由器,本教程不一定使用,请谨慎参考.

## 参考
- [https://github.com/aboutboy/kirkwood-88F6281](https://github.com/aboutboy/kirkwood-88F6281)
