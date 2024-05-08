# 小米Xiaomi路由器 BE6500 Pro 解锁SSH和科学上网教程
本教程一共分为两个视频，第一个是解锁SSH，第二个是安装ShellCrash科学上网。在小米原来的固件上安装科学上网软件，不影响路由器原有的功能，并且支持全屋科学上网。

## 小米路由器 BE6500 Pro 解锁SSH教程

### 第一步：下载固件和工具
- 小米路由器 BE6500 Pro 固件 1.0.46 版本，<a href="https://github.com/eujc/lyq/releases/download/ROM/miwifi_rd08_firmware_076b5_1.0.46.bin" target="_blank">点击下载>></a>
- 工具下载：<a href="https://github.com/eujc/lyq/releases/download/ROM/putty.zip" target="_blank">Putty下载>></a> ，MAC使用Termius，<a href="https://termius.com/download" target="_blank">点击下载>></a>
- 固件版本需要是1.0.46，如果不是这个版本，请使用 <a href="https://bigota.miwifi.com/xiaoqiang/tools/MIWIFIRepairTool.x86.zip" target="_blank">小米路由器修复工具</a> 完成固件降级，<a href="https://youtu.be/noBqKNq2MTk" target="_blank">降级教程</a>。

### 第二步：开启SSH
Windows用户可使用 <code>命令提示符</code> 、MacOS用户可使用 <code>终端</code> ，输入下列代码开启小米路由器 BE6500Pro 的SSH功能。<br>
请将 <STOK> 替换成 stok 码，注意：每次登录路由器后台 stok 码会改变。

    curl -X POST http://192.168.31.1/cgi-bin/luci/;stok=<STOK>/api/misystem/arn_switch -d "open=1&model=1&level=%0Anvram%20set%20ssh_en%3D1%0A"
    
    curl -X POST http://192.168.31.1/cgi-bin/luci/;stok=<STOK>/api/misystem/arn_switch -d "open=1&model=1&level=%0Anvram%20commit%0A"
    
    curl -X POST http://192.168.31.1/cgi-bin/luci/;stok=<STOK>/api/misystem/arn_switch -d "open=1&model=1&level=%0Ased%20-i%20's%2Fchannel%3D.*%2Fchannel%3D%22debug%22%2Fg'%20%2Fetc%2Finit.d%2Fdropbear%0A"
    
    curl -X POST http://192.168.31.1/cgi-bin/luci/;stok=<STOK>/api/misystem/arn_switch -d "open=1&model=1&level=%0A%2Fetc%2Finit.d%2Fdropbear%20start%0A"
