---
title: IntelliJ IDEA 配置 备忘录
categories: 技术
date: 2018-07-04 21:02:02
tags: 
  - 工具
  - JDK
---



#### 1. 配置JDK

1. [官网下载](http://www.oracle.com/technetwork/java/javase/downloads/index.html) 

2. 安装

3. 安装完成后，在 terminal 里输入 `/usr/libexec/java_homo` 查看 `JAVA_HOME` 的路径。

4. `sudo nano /etc/profile`

5. 添加

   ```bash
   JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_171.jdk/Contents/Home
   PATH=$JAVA_HOME/bin:$PATH:.
   CLASSPATH=$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar:.
   export JAVA_HOME
   export PATH
   export CLASSPATH
   ```

6. 要想马上生效，输入 `source /etc/profile` 运行profile配置。

7. 检查环境。输入 `echo $JAVA_HOME` 得到配置的路径，说明配置完毕。



#### 2. 常用设置

1. Theme: Relax Your Eyes Green

2. 代码补全取消区分大小写

   Preferences -> 搜索 code completion -> Case sensitive completion 选为 none。

3. 自动导包

![img](http://img.phperz.com/data/img/20150923/1443020024_1689.jpg)