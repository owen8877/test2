---
title: 1 隔壁老王的故事 (从新手到菜鸟的Linux教程)
tags:
  - cd
  - ls
id: 344
categories:
  - 从新手到菜鸟的Linux教程
date: 2016-06-01T22:32:10+08:00
---

好的，欢迎大家来到这篇教程。首先，我们认识一下故事的主角，隔壁老王。

![想密码想了我十分钟](/images/2016-06-1-story-of-neighbour-wang/Screenshot-from-2016-06-01-21-38-44.jpg)

老王是一个学习挺认真的同学，熟悉Microsoft办公套件的打开与关闭，能够默写主流编程语言的名字；他的理想是成为一名全栈工程师。他听说最好去学学Linux，因为这对一个程序员，或者未来的程序员有帮助。于是老王找到了我，让我教他用。

我说：“我也是新手啊。”

老王说：“你别装了，你看你都精神分裂了。”

我：“……”

果然我不适合写小说。

好吧，我们还是回归到正题上来吧。所以呢，接下来我将会以wang这个用户的身份，带大家一点点积累Linux使用的经验的。

<!--more-->

所以初识Linux（Ubuntu），我们登陆之后，先会看到这个：![](/images/2016-06-1-story-of-neighbour-wang/Screenshot-from-2016-06-01-21-39-29.jpg)不好意思，这不是一篇教你怎么用Unity（桌面环境）的文章；我们感兴趣的是命令行。按住Ctrl和Alt，再按下T键，就会弹出来通往新世界的大门：

![我在思考留这么大的空是为了干什么……](/images/2016-06-1-story-of-neighbour-wang/Screenshot-from-2016-06-01-22-01-01.jpg)

其实命令行还是有很多有趣的东西的，比如下面这个命令：
```bash
wang:~$ who am i
wang     pts/19       2016-06-01 22:00 (:1)
```
是不是很有趣的语法？

行走在bash的大地上，你会感到疑惑：我现在究竟在什么地方呢？可以干什么呢？事实上前一个问题的回答已经显现过了。看到`wang:~$`中间那个`~`没有？这个半角的波浪线（全角就不行←_←）代表的就是家目录的意思；其实它会被bash转义成为`/home/wang`（当然现在我们还不需要关心什么是“转义”），所以文件系统中是没有`~`这个地方的啦。

好了，如果我们想要查看当前目录下的文件，我们应该怎么办呢？`ls`命令就是为了列举文件(**l**i**s**t files)而编写的。要查看当前目录（现在是`~`）下的文件，输入`ls`并按回车：
```bash
wang:~$ ls
Desktop    Downloads         Music     Public     Videos
Documents  examples.desktop  Pictures  Templates
```
终端里应该能显示高亮的效果，方便我们区分文件的属性。

`ls`命令还有许多变体。比如`l`就是`ls`本身（可以少按一个键），`la`可以查看隐藏文件，`ll`~~大法好~~可以详细列出文件的信息：就像这样：
```bash
wang:~$ l
Desktop/    Downloads/        Music/     Public/     Videos/
Documents/  examples.desktop  Pictures/  Templates/

wang:~$ la
.bash_history  .dmrc             .ICEauthority  .profile     .xinputrc
.bash_logout   Documents         .local         Public       .xsession-errors
.bashrc        Downloads         .mozilla       Templates
.cache         examples.desktop  Music          Videos
.config        .gconf            Pictures       .viminfo
Desktop        .gnome            .pki           .Xauthority

wang:~$ ll
total 120
drwxr-xr-x 17 wang wang 4096  6月  1 21:59 ./
drwxr-xr-x  7 root root 4096  6月  1 21:36 ../
-rw-------  1 wang wang   63  6月  1 22:00 .bash_history
-rw-r--r--  1 wang wang  220  6月  1 21:36 .bash_logout
-rw-r--r--  1 wang wang 3768  6月  1 21:59 .bashrc
...
```
为了清晰起见，命令输出结果被我追加了一个换行符；事实上是没有的。

那如果我想要切换到某个文件夹下怎么办呢？那就用`cd`命令(**c**hange **d**irectory)。值得注意的是如果你不确定文件夹的名字，或者只记得一部分，可以先输入一部分，然后按Tab键补全：
```bash
wang:~$ cd P
Pictures/ Public/
```
输入一个`i`以后再按Tab键就会自动补全为`Pictures`，因为当前目录下只有一个以`Pi`开头的文件夹。

好的，我们已经切换到`~/Picutres`下面了，查看一下文件：
```bash
wang:~/Pictures$ ls
Screenshot from 2016-06-01 21-39-29.png
Screenshot from 2016-06-01 21-40-26.png
Screenshot from 2016-06-01 21-40-49.png
Screenshot from 2016-06-01 22-01-01.png
```
不好意思这些截图被你们看到了-_-

如果想要退回上一级菜单怎么办呢？难道输入`cd [parent]`吗？其实，父文件夹也是一个“文件”（这种特性我们之后会详细说到），那么“文件名”是什么呢？答案由`ll`来揭晓：
```bash
wang:~/Pictures$ ll
total 232
drwxr-xr-x  2 wang wang   4096  6月  1 22:01 ./
drwxr-xr-x 17 wang wang   4096  6月  1 21:59 ../
-rw-rw-r--  1 wang wang 179521  6月  1 21:39 Screenshot from 2016-06-01 21-39-29.png
...
```
你猜～对了！`.`是指向了当前目录，而`..`是指向了上一级目录。所以为了退出这个文件夹，我们只要输入`cd ..`就行了
```bash
wang:~/Pictures$ cd ..
wang:~$
```
注意到`$`前面显示路径的变化了没有？表示我们成功达到了我们的目的。

好了，今天的教程就到这里。至于老王的故事，我还是先好好想一想再说吧。
