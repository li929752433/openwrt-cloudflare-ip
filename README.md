## 使用 CloudFlare 优选 IP 加速 PassWall

使用此脚本需要在服务器搭建完后，开启 CloudFlare CDN功能才可实现！

首先确保系统安装了tar、wget、jq 程序，如果未安装，先运行命令：

opkg update

opkg install tar

opkg install wget

opkg install jq

主要需要修改的地方在于 passwall.xxxxxxxxxx.address 这几段,这几段主要来自于PassWall的配置文件

配置文件在 /etc/config/passwall  

搞定完所有要修改的地方后，建议试着运行一下。只需要把脚本复制到你想要的任何目录，再运行命令：

chmod +x cf-openwrt-auto.sh && bash cf-openwrt-auto.sh

如果你设置的都没啥问题，那么就可以直接在OpenWrt后台设置个计划任务。非常简单，找到系统 -> 计划任务，在文本框中填写：

0 4 * * 2,4,6 bash /path/cf-openwrt-auto.sh > /dev/null

0 4 * * 2,4,6的意思是在每周二、周四、周六的凌晨4点会自动运行一次。

具体教程可见：https://www.idleleo.com/04/5199

<br/>
<br/>

> _感谢以下项目：_

> _https://github.com/XIU2/CloudflareSpeedTest_
