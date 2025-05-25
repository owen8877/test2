---
title: 2 本apt具有超级牛力 (从新手到菜鸟的Linux教程)
tags:
  - apt
  - 彩蛋
id: 351
categories:
  - 从新手到菜鸟的Linux教程
date: 2016-06-02T19:59:11+08:00
---

不信？自己打个在终端里打个`apt-get`试试。
<!--more-->
那么`apt`究竟是何方神圣呢？

> [简析高持续性威胁（APT）的三个要素](http://netsecurity.51cto.com/art/201109/290445.htm "简析高持续性威胁（APT）的三个要素")
>
> 高持续性威胁（Advanced Persistent Threat）是以商业和政治为目的的一个网络犯罪类别……
不好意思看错了……以下是从维基百科搬运来的：
> **高级包装工具**（英语：**Advanced Packaging Tools**，缩写为**[APT](https://zh.wikipedia.org/wiki/APT "APT")**）是[Debian](https://zh.wikipedia.org/wiki/Debian "Debian")及其派生[发行版](https://zh.wikipedia.org/wiki/%E7%99%BC%E8%A1%8C%E7%89%88 "发行版")的[软件包](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E5%8C%85 "软件包")管理器。APT可以自动下载，配置，安装二进制或者源代码格式的[软件包](https://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E5%8C%85 "软件包")，因此简化了[Unix](https://zh.wikipedia.org/wiki/Unix "Unix")系统上管理软件的过程。

在没有`apt`的年代里，要安装一个软件有两种途径：一种是要下载二进制文件，并放入指定地点；第二种是下载源代码自行编译……不论哪一种听上去都相当麻烦。不过，既然这些事情都相当机械化，为什么不写个程序来管理安装这件事情呢？所以**包管理器**就是这么诞生的。不同Linux发行版有不同的包管理器；我们用的是`apt`。

在过去Ubuntu的版本中，我们要学习`apt-get`，`apt-cache`等命令以进行不同的操作，但是新系统中允许我们用单一`apt`完成全部工作（大概是用户吐槽那两个工具的子命令没有交集却要分开来使用）。`apt`后面可以添加的字命令有这些（别忘了最前面要加`sudo`哦）：

| 子命令           | 解释                           |
|:----------------:|:------------------------------:|
| `install` + 包名 | 安装-_-                        |
| `remove` + 包    | 卸载，但保留配置文件           |
| `purge` + 包名   | 卸载，但不保留配置文件         |
| `search` + 包名  | 在本地缓存的软件目录中查找软件 |
| `update`         | 刷新本地软件目录（不进行升级） |
| `upgrade`        | 从软件仓库更新软件             |

怎么样，还是相当好记的吧。下面就以安装网易云音乐为例试试。

![……](/images/2-this-apt-has-super-cow-power/Screenshot-from-2016-06-02-19-14-38.jpg)

还是算了。

那么我们安装`indicator-cpufreq`好了。以下是终端输出：
```bash
wang:~$ sudo apt install indicator-cpufreq
[sudo] password for wang:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  indicator-cpufreq
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 25.8 kB of archives.
After this operation, 615 kB of additional disk space will be used.
Get:1 http://cn.archive.ubuntu.com/ubuntu/ wily/universe indicator-cpufreq all 0.2.2-0ubuntu2 [25.8 kB]
Fetched 25.8 kB in 1s (19.5 kB/s)
Selecting previously unselected package indicator-cpufreq.
(Reading database ... 286376 files and directories currently installed.)
Preparing to unpack .../indicator-cpufreq_0.2.2-0ubuntu2_all.deb ...
Unpacking indicator-cpufreq (0.2.2-0ubuntu2) ...
Processing triggers for dbus (1.10.0-1ubuntu1) ...
Processing triggers for man-db (2.7.4-1) ...
Processing triggers for hicolor-icon-theme (0.15-0ubuntu1) ...
Setting up indicator-cpufreq (0.2.2-0ubuntu2) ...
Processing triggers for dbus (1.10.0-1ubuntu1) ...
```

* * *

P.S. `apt`彩蛋还真是多……
```bash
wang:~$ apt-get moo
(__)
(oo)
/------\/
/ | ||
* /\---/\
~~ ~~
..."Have you mooed today?"...
wang~:$ apt-get moo moo
(__)
_______~(..)~
,----\(oo)
/|____|,'
* /"\ /\
~ ~ ~ ~
..."Have you mooed today?"...
wang:~$ apt-get moo moo moo
\_/
m00h (__) -(_)-
\ ~Oo~___ / \
(..) |\
___________|_|_|_____________
..."Have you mooed today?"...
```
