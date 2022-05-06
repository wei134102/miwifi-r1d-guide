=========================================================================================
先看看我的路由文件


root@XiaoQiang:/# ls -la
drwxr-xr-x   22 root     root          1024 Jan 15 11:08 .
drwxr-xr-x   22 root     root          1024 Jan 15 11:08 ..
drwxrwxrwx    2 root     root          2048 Oct 16  2018 bin
drwxr-xr-x    7 root     root          4096 Jan  8 20:35 data
drwxr-xr-x    8 root     root          1680 Oct 16  2018 dev
drwxrwxrwx   35 root     root          4096 Oct 16  2018 etc
drwxr-xr-x    3 root     root            60 Oct 16  2018 extdisks
drwxrwxrwx   18 root     root          2048 Oct 16  2018 lib
drwx------    2 root     root       6710272 Oct 16  2018 lost+found
drwxr-xr-x    2 root     root          1024 Oct 16  2018 mnt
lrwxrwxrwx    1 root     root            13 Dec 31 19:40 opt -> /userdisk/opt
drwxr-xr-x    4 root     root          1024 Oct 16  2018 opt1
drwxr-xr-x    2 root     root          1024 Oct 16  2018 overlay
dr-xr-xr-x  142 root     root             0 Jan  1  1970 proc
drwxr-xr-x    2 root     root          1024 Oct 16  2018 readonly
drwxr-xr-x   22 root     root          1024 Jan 15 11:08 rom
lrwxrwxrwx    1 root     root            14 Jan 15 11:08 root -> /userdisk/root
drwxr-xr-x    2 root     root          1024 Oct 16  2018 root1
drwxrwxrwx    2 root     root          2048 Oct 16  2018 sbin
drwxr-xr-x   12 root     root             0 Jan  1  1970 sys
drwxr-xr-x   27 root     root          1240 Feb 17 19:42 tmp
drwxr-xr-x   38 root     root          4096 Jan 15 20:29 userdisk
drwxrwxrwx    9 root     root          1024 Oct 16  2018 usr
lrwxrwxrwx    1 root     root             4 Oct 16  2018 var -> /tmp
drwxr-xr-x   12 root     root          1024 Jan 15 15:04 www


其中有两条软连接，因为本身opt,root 所在分区太小了，不满足安装插件需求
  opt 做的软连接 opt -> /userdisk/opt  用来安装  mixbox插件库 以及entware软件
  root 做的软连接 root -> /userdisk/root  用来安装qbittorrent 本人不喜欢transmission

=======================================================================================

1.1qbittorrent-nox
上传到root/bin下面
使用方法一时说不清楚 请自行github
参考链接：
https://userdocs.github.io/qbittorrent-nox-static/#/install-qbittorrent
1.2  qbplus文件夹为QBittorrent 插件 

2.mixbox 
使用方法一时说不清楚 请自行github

参考链接

https://github.com/monlor/MIXBOX-ARCHIVE

3.QB自启动
1)putty miwifi
2)vim /etc/rc.local
exit 0 之前添加一下代码

=========================
sleep 30
nohup /root/bin/qbittorrent-nox -d

==================================

退出保存。重启实验。

