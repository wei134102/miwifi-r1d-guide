# miwifi-r1d-guide

1.小米路由器R1D主要参数：
处理器	博通Boardcom 1GHz双核 
DRAM内存	美光/三星256MB DDR3
Flash闪存	内置1TB硬盘/USB3.0芯片转接的
其他接口	1个USB2.0接口
天线类型	内置式，2.5g/5g
系统参数	Linux version 2.6.36 (jenkins@59cfa6095bf8) (gcc version 4.8.2 20130603 (prerelease) (crosstool-NG 1.19.0) ) #3 MiWiFi-R1D-2.25.213 SMP PREEMPT Tue Oct 16 11:44:14 UTC 2018


2.这台13年的产品适合做轻NAS，为什么选择这款路由呢，因为小米的产品存量大，某鱼价格非常便宜，基本不带硬盘价位50左右就可以入手，自己加块硬盘就可以，优点省电而且还有无线信号，下面介绍主要玩法。
3.1官方系统+mixbox插件玩法（极其推荐）
	优点：可以使用官方MIWIFI APP，高度方便可控路由，备份图片，数据非常方便，mixbox 下面有PT插件，网站等。
3.2第二系统TOMATO系统
优点：可脱离硬盘，系统直接在FLASH里面，对硬盘友好，缺点，不支持官方APP ，控制路由不方便。
3.3小米路由核心支持包 - Jack's Lab (jackslab.org)，更换这位大神的系统和内核，添加debian 7 Wheezy系统支持（可以使用apt-get命令安装软件）。
优点：debian 7 安装源，高度自由
缺点：无官方APP支持，不适合家用。

4.大家在用官方ROM刷玩系统以后，在将硬盘插到Ubuntu 系统下会发现 最大的分区被格式化成ext4分区，这样不便于使用，需要将最后的分区调整大小建议40G（路由系统识别为/userdisk），剩余分区格式为NTFS分区，这样这个NTFS分区就可以在WINDOWS上识别，如果系统坏了也可以还原备份文件，备份的图片什么的可以在NTFS 做个软连接到40g那个分区 ，这样所有备份的文件都可以拔下硬盘插到Windows系统识别。这个NTFS分区在路由系统是识别为 /extdisks,不必担心使用问题。后期如果硬盘坏了也可以window恢复数据能够识别。

