---
title: Linux设置PATH环境变量，实现通过PATH值指向指定可执行文件
date: 2020-11-15 14:10:39
tags: Linux
categories: Linux	
---
 Linux设置PATH环境变量，实现通过PATH值指向指定可执行文件
<!--more-->
## 输入 echo $PATH

```bash
cg@cg-RedmiBook-14:~$ echo $PATH
```
```
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

echo $PATH 显示当前PATH环境变量，该变量的值由一系列以冒号分隔的目录名组成。

如：/usr/local/bin:/bin:/usr/bin。当我们执行程序时shell自动跟据PATH变量的值去搜索该程序。

比如我们现在的工作目录是根目录/ ，有一个程序sunrise在/bin/目录下，我们可以在命令行输入/bin/sunrise 这样来执行它，还可以直接输入sunrise，这时shell会自动去寻找sunrise这个程序所在的完整路径，找到之后才会去执行该程序。

shell在搜索时先搜索PATH环境变量中的第一个目录，没找到再接着搜索，如果找到则执行它，不会再继续搜索。



## 例A

举例 我现在需要把MarkDown编辑器 Typora 设置到Linux PATH变量值中,

注意 通过Typora官网安装 apt命令安装的 默认会设置Linux PATH变量值 

因为我 习惯把安装的软件放在/opt/目录下 统一管理 造成了apt 设置PATH变量失效

所以重新设置一遍PATH值



输入 export PATH="/opt/typora:$PATH"

```bash
cg@cg-RedmiBook-14:~$ export PATH="/opt/typora:$PATH"
```

 

添加好 终端是无反应的

接着我们输入 

```bash
echo $PATH
```

我们发现 /opt/typora:已经添加进去了

```bash
cg@cg-RedmiBook-14:~$ echo $PATH
```
```
/opt/typora:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

接下来我们在任何目录下 都可以执行typora/下的 可执行文件了 
