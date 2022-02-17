本方法测试环境最新开发版
2.6.36 #3 MiWiFi-R1D-2.25.213 SMP PREEMPT Tue Oct 16 11:44:14 UTC 2018 armv7l GNU/Linux
=======================================================================================



*********************前提 ：必须开启ssh,  这个自行搜索**********************************

使用winscp等类似软件，连接路由器 打开SS窗口，以下命令都是在SSH窗口传输命令。

步骤：
1。备份  注意：/extdisks/sda5/backup 是你的备份路径，个人都不同，运行下面命令前替换
 1.1创建备份文件夹
  midir -p  /extdisks/sda5/backup
 1.2备份文件  注意：/extdisks/sda5/backup 是你的备份路径，个人都不同，运行下面命令前替换
  cp /usr/lib/lua/luci/controller/api/misystem.lua /extdisks/sda5/backup
  cp /usr/lib/lua/xiaoqiang/util/XQSysUtil.lua /extdisks/sda5/backup
  cp /usr/lib/lua/luci/view/web/*index.htm /extdisks/sda5/backup
  1.3查看你的备份文件夹backup下面是否有备份好的文件，有继续下一步

2.修改文件

2.1使用winscp等类似软件 将文件夹tmpok 上传到某一目录
2.2此条命令作用便是挂载路由根目录为读写
    mount -o remount rw /
2.3替换文件 注意：/extdisks/sda5/tmpok  是你上传的路径，个人都不同，运行下面命令前替换
   cp -rf /extdisks/sda5/tmpok/misystem.lua  /usr/lib/lua/luci/controller/api/
   cp -rf /extdisks/sda5/tmpok/XQSysUtil.lua  /usr/lib/lua/xiaoqiang/util/
   cp -rf /extdisks/sda5/tmpok/*index.htm     /usr/lib/lua/luci/view/web/

2.4 打开winscp控制台（ssh窗口），逐条运行以下命令：

rm -rf /tmp/luci-modulecache
mount -o remount ro /
现在刷新web管理首页已经可以看到cpu核心温度了
