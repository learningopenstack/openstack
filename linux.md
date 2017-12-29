# Linux入门指南 #

#linux基础#
##linux由来##
在Linux诞生之前，一直是Unix的天下。只不过当时Unix并不能免费获得，要想使用必须先购买授权，这在当时是非常昂贵的，很少有人能承担得起。

在这样的背景下，很多计算机爱好者非常渴望有一个便宜或者免费的操作系统供大家学习研究。1983年，计算机界的牛人Richard Stallman发起了一个计划，目的就是构建一套完全自由的操作系统，这个计划就是著名的GNU计划。所谓完全自由，就是要求加入GNU计划的所有软件都必须自由使用、自由更改、自由发布。也就是说，软件发布必须要发布它的源代码，这个源代码可以供别人自由使用，也可以随便更改，但是必须要把更改后的代码发布。当然了，光说不行，必须要有明文规定许可协议来制约大家如何自由，这套规定许可就是著名的GPL协议。

GNU计划发起后，涌现了Vi、Emacs、gcc等十分优秀的软件。但遗憾的是，一直没有一个比较完美的操作系统出现。直到1991年，芬兰大学生林纳斯•本纳第克特•托瓦兹（Linus Benedict Torvalds）基于兴趣开发了一个类Unix操作系统，一经发布便得到了广大爱好者的追捧，这个系统就是Linux。1994年，Linux加入GNU计划并采用GPL协议发布。自此，GNU/Linux真正实现了构建一套完全自由的操作系统的设想。


##Linux发行版 ###
linux是免费的，免费是指linux的内核免费
linux发行版是指将Linux内核与应用软件进行打包。

- Ubuntu
- RedHat
- Centos
- Debain
- Fedora
- SuSE
- OpenSUSE
- TurboLinux
- BluePoint
- RedFlag
- Xterm
- SlackWare

##Linux用户权限管理##

**Linux系统：** root的权限是最高的，相当于windows的administrator，拥有最高权限，能执行任何命令和操作。在系统中，通过UID来区分用户的权限级别，UID等于0，表示此用户具有最高权限，也就是管理员。其他的用户UID依次增加，通过/etc/passwd用户密码文件可以查看到每个用户的独立的UID。

每一个文件或者目录的权限，都包含一个用户权限、一个组的权限、其他人权限，例如下：
	
	[root@node1 ~]# ls -l monitor_log.sh
	-rw-r--r-- 1 root root 91 May  7 20:21 monitor_log.sh

改变某个文件的所有者或者所属的组，可以使用命令chown：

	chown  –R  test:test  monitor_log.sh

每个Linux文件具有四种访问权限：

- 可读r(4)
- 可写w(2)
- 可执行x(1)
- 无权限-(0)

文件类型：

- -表示文件
- d表示目录
- 等等

给某个文件授权，命令为chmod：
	
	chmod 777 monitor_log.sh

## linux基本命令 ##

**默认进入系统：**  
[root@localhost ~]#  //其中#代表当前是root用户登录，如果是$表示当前为普通用户。

****tap****
	
	神器 

****线上查询及帮助命令****

	help
	eg: mkdir –help

****文件和目录操作命令****

	ls tree pwd mkdir rmdir cd touch cp mv rm ln find

****查看文件及内容处理命令****

	cat tac more less head tail cut split paste sort uniq wc iconv dos2unix file diff vimd ff chattr lsattr rev grep

****文件压缩及解压缩命令****

	tar unzip gzip zip

****信息显示命令****

	uname hostname dmesg uptime file stat du df top free date cal

****搜索文件命令****

	which find whereis locate

****用户管理命令****

	useradd usermod userdel groupadd passwd chage id su visudo sudo

****基础网络操作命令****

	telnet ssh scp wget ping route ifconfig ifup ifdown netstat

****深入网络操作命令****

	lsof route mail mutt nslookup dig

****有关磁盘文件系统的命令****

	mount umount df du fsck dd dumpe2fs dump

****关机和查看系统信息的命令****

	shutdown halt init

****系统管理相关命令****

	uptime top free vmstat mpstat iostat sar chkconfig

****系统安全相关命令****

	chmod chown chgrp chage passwd su sudo umask chattr lsattr

****查看系统用户登陆信息的命令****

	whoami who w last lastlog users finger

## linux系统管理 ##

- / 根目录 
- /bin 存放必要的命令 
- /boot 存放内核以及启动所需的文件
- /dev 存放设备文件 
- /etc 存放系统配置文件 
- /home 普通用户的宿主目录，用户数据存放在其主目录中 
- /lib 存放必要的运行库 
- /mnt 存放临时的映射文件系统，通常用来挂载使用。
- /proc 存放存储进程和系统信息 
- /root 超级用户的主目录 
- /sbin 存放系统管理程序 
- /tmp 存放临时文件
- /usr 存放应用程序，命令程序文件、程序库、手册和其它文档。 
- /var 系统默认日志存放目录
- .    当前目录
- ..   当前目录的上层目录


## linux常见服务 ##

- nginx、apache
- mysql，mariadb
- FTP服务器
- NTP时间服务器
- DHCP服务器
- Samba服务器
- NFS服务器


## linux rpm、yum ##