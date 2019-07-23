# [manjaro xfce 18.0 踩坑记录](https://www.cnblogs.com/elinuxboy/p/10123877.html)



**目录**

-   1 简介
    -   [1.1 Manjaro Linux](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label0_0)
    -   [1.2 开发桌面环境](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label0_1)
-   [2 自动打开 NumLock](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label1)
-   3 系统快照
    -   [3.1 安装timeshift](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label2_0)
    -   [3.2 使用timeshift创建系统快照](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label2_1)
-   4 国内源设置
    -   [4.1 manjaro官方软件仓库](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label3_0)
    -   [4.2 非官方仓库（Arch Linux 中文社区仓库）](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label3_1)
-   [5 安装yaourt以及pacaur](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label4)
-   6 软件安装时下载加速
    -   [6.1 使用aria2c多线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label5_0)
    -   [6.2 使用Axel单线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label5_1)
-   [7 安装被锁定的问题](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label6)
-   [8 升级系统](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label7)
-   9 常见的软件安装
    -   [9.1 pacman 基本用法](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_0)
    -   [9.2 安装中文输入法](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_1)
    -   [9.3 安装字体](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_2)
    -   [9.4 安装vim](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_3)
    -   [9.5 安装markdown编辑器](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_4)
    -   [9.6 安装git](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_5)
    -   [9.7 安装smartGit](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_6)
    -   [9.8 安装图形化的解压软件](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_7)
    -   [9.9 安装bat替代cat](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_8)
    -   [9.10 安装护眼软件红移redshift](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_9)
    -   [9.11 安装gnome磁盘管理](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_10)
    -   [9.12 安装截图软件（可编辑）](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_11)
    -   [9.13 安装google浏览器](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_12)
    -   [9.14 安装uGet](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_13)
    -   [9.15 安装网易云音乐](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_14)
    -   [9.16 安装osdlyrics（本地音乐播放器显示歌词需要）](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_15)
    -   [9.17 安装WPS-office](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_16)
    -   [9.18 安装有道词典](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_17)
    -   [9.19 安装ClamAV](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_18)
    -   [9.20 安装sublime-text-3](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_19)
    -   [9.21 安装虚拟机](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_20)
    -   [9.22 安装QQ](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_21)
    -   [9.23 安装Tim](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_22)
    -   [9.24 安装微信](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_23)
    -   [9.25 安装oh my zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label8_24)
-   10 XFCE图标主题美化
    -   [10.1 安装图标](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label9_0)
    -   [10.2 安装主题](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label9_1)
    -   [10.3 设置](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label9_2)
-   [11 优化系统启动速度](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label10)
-   [12 将npm的注册表源设置为国内的镜像](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label11)
-   13 问题与解决
    -   [13.1 安装中遇到的问题](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label12_0)
    -   [13.2 警告：xxx本地比xxx的版本更新](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label12_1)
    -   [13.3 aria2c下载xxx.db.sig出现错误](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label12_2)
    -   [13.4 错误：无法注册 ‘archlinuxcn’ 数据库 (数据库已登记)](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label12_3)
-   [附录I：/etc/pacman.conf](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label13)
-   [附录II：/etc/makepkg.conf](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label14)
-   [附录III：/etc/pacman.d/mirrorlist](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label15)
-   [附录IV：.zshrc](https://www.cnblogs.com/elinuxboy/p/10123877.html#_label16)

 

------

# manjaro xfce 18.0 踩坑记录

[1 简介](https://www.cnblogs.com/elinuxboy/p/10123877.html#h1)[1.1 Manjaro Linux](https://www.cnblogs.com/elinuxboy/p/10123877.html#h11manjarolinux)[1.2 开发桌面环境](https://www.cnblogs.com/elinuxboy/p/10123877.html#h12)[2 自动打开 NumLock](https://www.cnblogs.com/elinuxboy/p/10123877.html#h2numlock)[3 系统快照](https://www.cnblogs.com/elinuxboy/p/10123877.html#h3)[3.1 安装timeshift](https://www.cnblogs.com/elinuxboy/p/10123877.html#h31timeshift)[3.2 使用timeshift创建系统快照](https://www.cnblogs.com/elinuxboy/p/10123877.html#h32timeshift)[4 国内源设置](https://www.cnblogs.com/elinuxboy/p/10123877.html#h4)[4.1 manjaro官方软件仓库](https://www.cnblogs.com/elinuxboy/p/10123877.html#h41manjaro)[4.1.1 自动寻找最快的源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h411)[4.1.2 选择源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h412)[4.1.3 更新源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h413)[4.2 非官方仓库（Arch Linux 中文社区仓库）](https://www.cnblogs.com/elinuxboy/p/10123877.html#h42archlinux)[4.2.1 手动添加archlinuxcn清华源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h421archlinuxcn)[4.2.2 更新源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h422)[4.2.3 安装archlinuxcn-keyring包导入GPG key：](https://www.cnblogs.com/elinuxboy/p/10123877.html#h423archlinuxcnkeyringgpgkey)[4.2.4 再次更新源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h424)[5 安装yaourt以及pacaur](https://www.cnblogs.com/elinuxboy/p/10123877.html#h5yaourtpacaur)[6 软件安装时下载加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h6)[6.1 使用aria2c多线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h61aria2c)[6.1.1 安装aria2c](https://www.cnblogs.com/elinuxboy/p/10123877.html#h611aria2c)[6.1.2 配置pacman多线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h612pacman)[6.1.3 配置yaourt多线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h613yaourt)[6.2 使用Axel单线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h62axel)[6.2.1 安装axel](https://www.cnblogs.com/elinuxboy/p/10123877.html#h621axel)[6.2.2 配置pacman单线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h622pacman)[6.2.3 配置yaourt单线程多链接加速](https://www.cnblogs.com/elinuxboy/p/10123877.html#h623yaourt)[6.2.4 然后更新数据源](https://www.cnblogs.com/elinuxboy/p/10123877.html#h624)[7 安装被锁定的问题](https://www.cnblogs.com/elinuxboy/p/10123877.html#h7)[8 升级系统](https://www.cnblogs.com/elinuxboy/p/10123877.html#h8)[9 常见的软件安装](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9)[9.1 pacman 基本用法](https://www.cnblogs.com/elinuxboy/p/10123877.html#h91pacman)[9.1.1 安装软件](https://www.cnblogs.com/elinuxboy/p/10123877.html#h911)[9.1.2 删除软件](https://www.cnblogs.com/elinuxboy/p/10123877.html#h912)[9.1.3 清空缓存](https://www.cnblogs.com/elinuxboy/p/10123877.html#h913)[9.1.4 查询](https://www.cnblogs.com/elinuxboy/p/10123877.html#h914)[9.1.5 同步文件数据库](https://www.cnblogs.com/elinuxboy/p/10123877.html#h915)[9.1.6 升级系统](https://www.cnblogs.com/elinuxboy/p/10123877.html#h916)[9.2 安装中文输入法](https://www.cnblogs.com/elinuxboy/p/10123877.html#h92)[9.3 安装字体](https://www.cnblogs.com/elinuxboy/p/10123877.html#h93)[9.4 安装vim](https://www.cnblogs.com/elinuxboy/p/10123877.html#h94vim)[9.4.1 超强vim配置](https://www.cnblogs.com/elinuxboy/p/10123877.html#h941vim)[9.5 安装markdown编辑器](https://www.cnblogs.com/elinuxboy/p/10123877.html#h95markdown)[9.6 安装git](https://www.cnblogs.com/elinuxboy/p/10123877.html#h96git)[9.7 安装smartGit](https://www.cnblogs.com/elinuxboy/p/10123877.html#h97smartgit)[9.8 安装图形化的解压软件](https://www.cnblogs.com/elinuxboy/p/10123877.html#h98)[9.9 安装bat替代cat](https://www.cnblogs.com/elinuxboy/p/10123877.html#h99batcat)[9.10 安装护眼软件红移redshift](https://www.cnblogs.com/elinuxboy/p/10123877.html#h910redshift)[9.11 安装gnome磁盘管理](https://www.cnblogs.com/elinuxboy/p/10123877.html#h911gnome)[9.12 安装截图软件（可编辑）](https://www.cnblogs.com/elinuxboy/p/10123877.html#h912-1)[9.13 安装google浏览器](https://www.cnblogs.com/elinuxboy/p/10123877.html#h913google)[9.14 安装uGet](https://www.cnblogs.com/elinuxboy/p/10123877.html#h914uget)[9.15 安装网易云音乐](https://www.cnblogs.com/elinuxboy/p/10123877.html#h915-1)[9.16 安装osdlyrics（本地音乐播放器显示歌词需要）](https://www.cnblogs.com/elinuxboy/p/10123877.html#h916osdlyrics)[9.17 安装WPS-office](https://www.cnblogs.com/elinuxboy/p/10123877.html#h917wpsoffice)[9.18 安装有道词典](https://www.cnblogs.com/elinuxboy/p/10123877.html#h918)[9.19 安装ClamAV](https://www.cnblogs.com/elinuxboy/p/10123877.html#h919clamav)[9.20 安装sublime-text-3](https://www.cnblogs.com/elinuxboy/p/10123877.html#h920sublimetext3)[9.21 安装虚拟机](https://www.cnblogs.com/elinuxboy/p/10123877.html#h921)[9.22 安装QQ](https://www.cnblogs.com/elinuxboy/p/10123877.html#h922qq)[9.23 安装Tim](https://www.cnblogs.com/elinuxboy/p/10123877.html#h923tim)[9.24 安装微信](https://www.cnblogs.com/elinuxboy/p/10123877.html#h924)[9.24.1 命令直接安装](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9241)[9.24.2 源码编译安装](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9242)[9.24.3 使用发布版](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9243)[9.25 安装oh my zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#h925ohmyzsh)[9.25.1 查看系统是否安装了zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9251zsh)[9.25.2 查看系统当前使用的shell](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9252shell)[9.25.3 切换shell为zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9253shellzsh)[9.25.4 下载安装 oh my zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9254ohmyzsh)[9.25.5 配置oh my zsh](https://www.cnblogs.com/elinuxboy/p/10123877.html#h9255ohmyzsh)[10 XFCE图标主题美化](https://www.cnblogs.com/elinuxboy/p/10123877.html#h10xfce)[10.1 安装图标](https://www.cnblogs.com/elinuxboy/p/10123877.html#h101)[10.2 安装主题](https://www.cnblogs.com/elinuxboy/p/10123877.html#h102)[10.3 设置](https://www.cnblogs.com/elinuxboy/p/10123877.html#h103)[11 优化系统启动速度](https://www.cnblogs.com/elinuxboy/p/10123877.html#h11)[12 将npm的注册表源设置为国内的镜像](https://www.cnblogs.com/elinuxboy/p/10123877.html#h12npm)[13 问题与解决](https://www.cnblogs.com/elinuxboy/p/10123877.html#h13)[13.1 安装中遇到的问题](https://www.cnblogs.com/elinuxboy/p/10123877.html#h131)[13.2 警告：xxx本地比xxx的版本更新](https://www.cnblogs.com/elinuxboy/p/10123877.html#h132xxxxxx)[13.2.1 解决办法](https://www.cnblogs.com/elinuxboy/p/10123877.html#h1321)[13.3 aria2c下载xxx.db.sig出现错误](https://www.cnblogs.com/elinuxboy/p/10123877.html#h133aria2cxxxdbsig)[13.3.1 解决办法](https://www.cnblogs.com/elinuxboy/p/10123877.html#h1331)[13.4 错误：无法注册 ‘archlinuxcn’ 数据库 (数据库已登记)](https://www.cnblogs.com/elinuxboy/p/10123877.html#h134archlinuxcn)[附录I：/etc/pacman.conf](https://www.cnblogs.com/elinuxboy/p/10123877.html#hietcpacmanconf)[附录II：/etc/makepkg.conf](https://www.cnblogs.com/elinuxboy/p/10123877.html#hiietcmakepkgconf)[附录III：/etc/pacman.d/mirrorlist](https://www.cnblogs.com/elinuxboy/p/10123877.html#hiiietcpacmandmirrorlist)[附录IV：.zshrc](https://www.cnblogs.com/elinuxboy/p/10123877.html#hivzshrc)

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 1 简介



### 1.1 Manjaro Linux

Manjaro Linux是一个基于Arch Linux的发行版，继承了后者**轻快**、**滚动式更新**、**AUR软件多**的==优点==，同时又**改善了**后者对新手不友好、软件包过于激进、不够稳定的==缺点==，是最能拿来用、最好用的Linux发行版。

它不仅**开箱即用**，**界面人性化**，**轻快不卡慢**，稳定无崩溃，**安静无弹窗**，最最可喜的是**软件超多**！相信你用了Manjaro之后，再不会折腾、也不会再抛弃这个发行版了。



### 1.2 开发桌面环境

我对桌面环境的需求次序（优先级由高到低）：

>   系统性能好，占用资源少——》软件数量多——》对用户友好，易安装，易使用——》界面美观

-   性能

    对**系统性能**的要求，必须要足够好，占用资源少，给开发留下的资源越多越好。

    作为一个开发者（程序员），想要提工作高效率，对系统性能的要求几乎达到苛刻的地步。

    因为开发者在处理一个问题时，动则要调用大量工具，或者同时打开十几、几十、上百个网页来搜索网上的解决方案，而firefox或chrome等上网工具都是吃内存大户（牺牲空间复杂度换来快速的时间复杂度），有时候必须牺牲一些后台程序以加快系统速度适应开发者的需要。

    而Manjaro Linux发行版和Xfce桌面都具有快速、轻量、加载程序快速、占用的系统资源少的优点。

-   软件

    为了节省不必要的折腾时间，开发者手头上的工具是越多越好、越容易获取越好。

    centos、slackware这些软件奇缺或者需要非常复杂的途径才能找到安装源的系统就没必要尝试了。

    ubuntu系软件比较丰富，但QQ/TIM这样的基本软件还需要折腾一番，还未必能稳定使用。

    [arch linux系软件包异常丰富](https://www.lulinux.com/archives/2787)，无情碾压deb和rpm系诸多发行版，例如manjaro下可以一条命令安装好无比稳定、功能全面的deepinwine-tim或deepinwine-qq。

-   对用户友好

    对任何一个工作者来说，时间就是衡量一切价值的标准，节省时间就是延长生命尺度。拿archlinux为反面典型，虽然其性能高可以节省工作时间，但是如果安装它都要从头开始学习ABC，那价值就大打折扣。就安装系统的便捷性来说，archlinux、gentoo、lfs这样的系统真没必要尝试。

-   界面外观

    为了性能，必须牺牲酷炫的外观，过炫的桌面影响桌面性能；但是过于简单的桌面需要花时间配置还不一定能完全配置好，也是影响工作效率。所以，外观普通即可，默认桌面选择xfce4、lxde、mate甚至仿制windows界面都是不错的。

综合考虑下，以下是我对一些发行版及桌面的排序（仅代表个人观点）：

-   发行版：

>   manjaro——》mint——》ubuntu——》debian——》其他

-   桌面环境

>   xfce 4——》mate/gnome-classic——》cinnamon——》lxde——》其他

我选择的开发桌面环境：

-   manjaro-xfce-18.0-stable（第一选择）
-   linuxmint-19-xfce
-   ubuntu-16.04.5-desktop

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 2 自动打开 NumLock

确保已经安装 numlockx, 然后编辑 /etc/lightdm/lightdm.conf文件，在末尾添加以下几行:

```shell
1[Seat:*]
2greeter-setup-script=/usr/bin/numlockx on
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 3 系统快照



### 3.1 安装timeshift

```
sudo pacman -S timeshift
```



### 3.2 使用timeshift创建系统快照

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111028661-336226830.png)

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 4 国内源设置



### 4.1 manjaro官方软件仓库

#### 4.1.1 自动寻找最快的源

```
sudo pacman-mirrors -i -c China -m rank
```



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看详细内容</summary></details>



#### 4.1.2 选择源

在弹出窗口中选择排第一位的源（这里选择清华大学tsinghua的源）然后点击“OK”，再次单击“确定”即可选择好最快的源。

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111114015-343509629.png)

#### 4.1.3 更新源

```
sudo pacman -Sy
```



### 4.2 非官方仓库（Arch Linux 中文社区仓库）

Arch Linux 中文社区仓库 是由 Arch Linux 中文社区驱动的非官方用户仓库。包含中文用户常用软件、工具、字体/美化包等。

完整的包信息列表（包名称/架构/维护者/状态）请 [点击这里](https://github.com/archlinuxcn/repo) 查看。

-   官方仓库地址：[http://repo.archlinuxcn.org](http://repo.archlinuxcn.org/)
-   镜像地址: <https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/>

#### 4.2.1 手动添加archlinuxcn清华源

```
sudo vim /etc/pacman.conf
```

用上面的命令编辑/etc/pacman.conf，在最下方添加（这里使用清华大学的源）：

```shell
1[archlinuxcn]
2Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

详情参见附录I。

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111509383-263018155.png)

#### 4.2.2 更新源

```
sudo pacman -Sy
```

#### 4.2.3 安装archlinuxcn-keyring包导入GPG key：

```
sudo pacman -S archlinuxcn-keyring
```

#### 4.2.4 再次更新源

```
sudo pacman -Sy
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 5 安装yaourt以及pacaur

为了安装使用AUR方便，也可以额外安装yaourt以及pacaur

```
sudo pacman -S yaourt pacaur
```

**注意：**使用使用yaourt安装软件时：

>   a.不需要使用sudo否则报root错误；
>
>   b.在提示调用vim时 输入vim然后回车；
>
>   c.如果不想输入vim: 修改~/.zshrc 文件文件最后加入export VISUAL=“vim” 即可。

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 6 软件安装时下载加速

设置替换wget或者curl下载命令。以下在配置时，aria2c和axel使用其中一种即可（这里使用aria2c）。



### 6.1 使用aria2c多线程多链接加速

aria2c 是一个自由、开源、轻量级多协议和多源的命令行下载工具。

aria2c 支持 HTTP/HTTPS、FTP、SFTP、 BitTorrent 和 Metalink 协议。

aria2c 可以通过内建的 JSON-RPC 和 XML-RPC 接口来操纵。

aria2c 下载文件的时候，自动验证数据块。它可以通过多个来源或者多个协议下载一个文件，并且会尝试利用你的最大下载带宽。

aria2c 支持多线程，可以使用多个源或协议下载文件，确实可以加速并尽可能多的完成下载。

#### 6.1.1 安装aria2c

```
sudo pacman -Sy aria2c
```

#### 6.1.2 配置pacman多线程多链接加速

编辑pacman配置文件/etc/pacman.conf，找到Xfercommand修改成如下：

```shell
1......
2# aria2c 多线程多链接
3XferCommand = /usr/bin/aria2c --allow-overwrite=true --log-level=error -l aria2c-error.log -c -m2 -x 8 -s 8 -j 8 -d $(dirname %o) -o $(basename %o) %u
4......
```

#### 6.1.3 配置yaourt多线程多链接加速

编辑makepkg配置文件/etc/makepkg.conf，找到DLAGENTS修改成如下



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看详细内容</summary></details>



详情请参见附录II。



### 6.2 使用Axel单线程多链接加速

Axel 是一个轻量级下载程序，它和其他加速器一样，对同一个文件建立多个连接，每个连接下载单独的文件片段以更快地完成下载。

Axel 支持 HTTP、HTTPS、FTP 和 FTPS 协议。它也可以使用多个镜像站点下载单个文件，所以，Axel 可以加速下载高达 40％（大约，我个人认为）。它非常轻量级，因为它没有依赖并且使用非常少的 CPU 和内存。

Axel 一步到位地将所有数据直接下载到目标文件（LCTT 译注：而不是像其它的下载软件那样下载成多个文件块，然后拼接）。

注意：不支持在单条命令中下载两个文件。

#### 6.2.1 安装axel

~~`sudo pacman -S axel`~~

#### 6.2.2 配置pacman单线程多链接加速

编辑pacman配置文件/etc/pacman.conf，找到Xfercommand修改成如下：

```shell
1......
2# axel 单线程多链接
3XferCommand = /usr/bin/axel -a -n 16 %u -o %o
4......
```

#### 6.2.3 配置yaourt单线程多链接加速

编辑makepkg配置文件/etc/makepkg.conf，找到DLAGENTS修改成如下



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看详细内容</summary></details>



#### 6.2.4 然后更新数据源

```
sudo pacman -Syy
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 7 安装被锁定的问题

**注意：**出现无法锁定database的错误时，在**确认没有安装任务时**运行以下命令删除锁定：

```
sudo rm /var/lib/pacman/db.lck
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 8 升级系统

```
sudo pacman -Syu
```

或者

```
yaourt -Syu
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 9 常见的软件安装



### 9.1 pacman 基本用法

#### 9.1.1 安装软件

```bash
 1# 安装或者升级单个软件包，或者一列软件包（包含依赖包），使用如下命令：
 2sudo pacman -S pkg_name1 pkg_name2 ...
 3
 4# 安装一个本地包(不从源里下载）：
 5sudo pacman -U /path/to/package/package_name-version.pkg.tar.xz
 6
 7# 安装一个远程包（不在 pacman 配置的源里面）：
 8sudo pacman -U http://www.example.com/repo/example.pkg.tar.xz
 9
10# 下载包而不安装它：
11sudo pacman -Sw pkg_name
```

#### 9.1.2 删除软件

```bash
 1# 删除指定安装包，但是保留其全部已安装的依赖关系
 2sudo pacman -R pkg_name 
 3
 4# 删除指定软件包，以及没有被其他已安装软件包使用的依赖关系。 
 5sudo pacman -Rs pkg_name 
 6
 7# 删除软件包和所有依赖这个软件包的程序:
 8# 警告: 此操作是递归的，请小心检查，可能会一次删除大量的软件包。
 9sudo pacman -Rsc pkg_name
10
11# 删除软件包，但是不删除依赖这个软件包的其他程序：
12sudo pacman -Rdd pkg_name
```

#### 9.1.3 清空缓存

```bash
1# 清除未安装软件包的缓存 
2sudo pacman -Sc 
```

#### 9.1.4 查询

```bash
 1# 在包数据库中查询软件包，查询位置包含了软件包的名字和描述(不指定string，则列出所有已安装的包)：
 2pacman -Ss string1 string2 ...
 3
 4# 查询包含某个文件的包名     
 5pacman -Fs pkg_name
 6
 7# 查询远程库中软件包包含的文件：
 8pacman -Fl pkg_name
 9
10# 获取已安装软件包所包含文件的列表：
11pacman -Ql pkg_name
12
13# 查询已安装的软件包(不指定string，则列出所有已安装的包)：
14pacman -Qs string1 string2 ...
15
16# 显示软件包的详尽的信息：
17sudo pacman -Si pkg_name
18
19# 查询本地安装包的详细信息：
20sudo pacman -Qi pkg_name
```

#### 9.1.5 同步文件数据库

```bash
1# 同步文件数据库:
2sudo pacman -Fy
```

#### 9.1.6 升级系统

```bash
1# 升级整个系统,这个命令会同步非本地(local)软件仓库并升级系统的软件包：
2sudo pacman -Syu
3
4# 升级系统时安装其他软件包：
5sudo pacman -Syu pkg_name1 pkg_name2 ...
6
7# 强制 pacman 刷新软件包列表，每次修改镜像之后都应该使用
8sudo pacman -Syyu
```



### 9.2 安装中文输入法

-   安装小企鹅fcitx：

*fcitx安装后会默认安装了拼音和五笔输入法。*

```
sudo pacman -S fcitx fcitx-im fcitx-configtool
```

需要修改配置文件 ~/.xprofile，添加如下语句：

```shell
1#fcitx
2export GTK_IM_MODULE=fcitx    
3export QT_IM_MODULE=fcitx    
4export XMODIFIERS="@im=fcitx"
```

-   安装其他中文输入法

    谷歌拼音输入法

    `sudo pacman -S fcitx-googlepinyin`

启动fcitx并设置输入法之后就可以使用中文输入法啦，如果异常请重新登录或者重启！！



### 9.3 安装字体

```
sudo pacman -S ttf-dejavu wqy-zenhei wqy-microhei ttf-monaco
```

要使用新安装的字体，需要再设置里自行选择。

-   设置——》外观——》字体——》选择默认字体和默认等宽字体



### 9.4 安装vim

```
sudo pacman -S vim
```

#### 9.4.1 超强vim配置

项目地址：https://github.com/elinuxboy/vim-deprecated

使用下面的命令自动安装配置：

```
wget -qO- https://raw.githubusercontent.com/elinuxboy/vim-deprecated/master/setup.sh | sh -x
```

或者用另一种方式自动安装：

```shell
1wget https://raw.githubusercontent.com/elinuxboy/vim-deprecated/master/setup.sh
2chmod +x setup.sh
3./setup.sh
```



### 9.5 安装markdown编辑器

以下只需要使用其中一种或几种。

`yaourt -S typora`（推荐使用）

```
sudo pacman -S remarkable
yaourt -S haroopad
sudo pacman -S retext
```



### 9.6 安装git

```
sudo pacman -S git
```

设置个人github信息

```
git config --global user.name "github昵称"
git config --global user.email "注册邮箱"
```



### 9.7 安装smartGit

一个Git客户端。archlinux/manjaro的主源里就有它。

```
yaout -S smartgit
```



### 9.8 安装图形化的解压软件

```
sudo pacman -S p7zip file-roller unrar
```



### 9.9 安装bat替代cat

```
sudo pacman -S bat
```



### 9.10 安装护眼软件红移redshift

```
sudo pacman -S redshift
```



### 9.11 安装gnome磁盘管理

```
sudo pacman -S gnome-disk-utility
```



### 9.12 安装截图软件（可编辑）

```
yaourt -S hotshots
```

**注意**：因为网络问题，这里可能需要对PKGBUILD做一些修改，将http改为https。



### 9.13 安装google浏览器

```
sudo pacman -S google-chrome
```



### 9.14 安装uGet

Linux 下最好的下载管理器

```
sudo pacman -S uget
```



### 9.15 安装网易云音乐

```
yaourt -S netease-cloud-music
```



### 9.16 安装osdlyrics（本地音乐播放器显示歌词需要）

```
sudo pacman -S osdlyrics
```



### 9.17 安装WPS-office

```
sudo pacman -S wps-office
```



### 9.18 安装有道词典

有道词典。

```
yaourt -S youdao-dict
```



### 9.19 安装ClamAV

Clam 防病毒软件（命令行）

```
sudo pacman -S clamav
```

Clam 防病毒软件（客户端）

```
sudo pacman -S clamtk
```



### 9.20 安装sublime-text-3

输入法修复版本

```
yaourt -S sublime-text-3-imfix
```

*如果默认的拼音输入法还是无法使用，需要安装其他中文输入法。如谷歌拼音/搜狗拼音等。*



### 9.21 安装虚拟机

```
yaourt -S vmware-workstation
```

**注意：**如果出现vmmod找不到的问题，需要安装linux-headers后再一次安装，之后重新登陆后即可。



### 9.22 安装QQ

```
yaourt -S deepin.com.qq.im
```



### 9.23 安装Tim

```
yaourt -S deepin.com.qq.office
```



### 9.24 安装微信

微信，公认最好的，是electronic-wechat。

#### 9.24.1 命令直接安装

```
yaourt -S electronic-wechat
```

#### 9.24.2 源码编译安装

在下载和运行这个项目之前，你需要在电脑上安装 [Git](https://git-scm.com/) 和 [Node.js](https://nodejs.org/en/download/) (来自 [npm](https://www.npmjs.com/))。在命令行中输入:

-   下载仓库

```
git clone https://github.com/geeeeeeeeek/electronic-wechat.git
```

-   进入源码目录

```
cd electronic-wechat
```

-   安装, 运行应用

```
sudo npm install && sudo npm start
```

-   根据你的平台打包应用:

```
sudo npm run build:linux
```

#### 9.24.3 使用发布版

[开箱即用的稳定版应用](https://github.com/geeeeeeeeek/electronic-wechat/releases)

```bash
1tar xvf electronic-wechat-linux-x64.tar.gz
2cd electronic-wechat-linux-x64
3./electronic-wechat %U
```

可以给他添加快捷方式



### 9.25 安装oh my zsh

#### 9.25.1 查看系统是否安装了zsh

```
cat /etc/shells
1# Pathnames of valid login shells.
2# See shells(5) for details.
3
4/bin/sh
5/bin/bash
6/bin/zsh
7/usr/bin/zsh
8/usr/bin/git-shell
```

-   如果已经安装zsh,则会多出来以下条目

    ```shell
    1/bin/zsh
    2/usr/bin/zsh
    ```

#### 9.25.2 查看系统当前使用的shell

```
1----
$ echo $SHELL
1/bin/bash
```

#### 9.25.3 切换shell为zsh

```
$ chsh -s /bin/zsh
```

如果要切换回去bash：

```
chsh -s /bin/bash
```

重启生效,如下所示:



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看详细内容</summary></details>



-   查看当前shell

```
$ echo $SHELL
1/bin/zsh
```

#### 9.25.4 下载安装 oh my zsh

```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```

完成后如下所示:



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看详细内容</summary></details>



#### 9.25.5 配置oh my zsh

-   安装autojump自动跳转插件

```shell
1sudo pacman -S autojump
2echo ". /usr/share/autojump/autojump.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
3source .zshrc
```

-   安装zsh-syntax-highlighting语法高亮插件

```shell
1git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
2echo "source $ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
3source .zshrc
```

-   安装zsh-autosuggestions语法历史记录插件

```shell
1git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
2echo "source $ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
3source .zshrc
```

-   安装自动补全插件incr

```shell
1cd $ZSH_CUSTOM/plugins
2mkdir incr
3cd incr
4wget http://mimosa-pudica.net/src/incr-0.2.zsh
5echo "source $ZSH_CUSTOM/plugins/incr/incr*.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
6source .zshrc
```

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111451681-1556416322.png)

详细的.zshrc请参见附录IV。

-   修改主题

修改.zshrc文件

```shell
1vim ~.zshrc
```

找到ZSH_THEME=“robbyrussell”，修改为：ZSH_THEME=“ys”；

```shell
1......
2ZSH_THEME="ys"
3......
```

更新配置

```shell
1source .zshrc
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 10 XFCE图标主题美化



### 10.1 安装图标

```
yaourt -S numix-circle-icon-theme-git
sudo pacman -S papirus-icon-theme
```



### 10.2 安装主题

```
sudo pacman -S arc-gtk-theme
```



### 10.3 设置

-   主题：设置——》外观——》样式——》arc
-   图标：设置——》外观——》图标——》numix circle

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 11 优化系统启动速度

Arch Linux 的 systemd-analyze 是个很不错的工具，利用它你可以很直观地观察到系统启动的时间都花到哪儿去了：

```
systemd-analyze
```

我注意到打开 AHCI 后，内核和用户空间的载入速度明显提高了，总启动时间从约 30 秒缩短到 20 秒，效果非常明显。

用下面这个命令，可以了解到是什么东西启动最慢：

```
systemd-analyze blame
```

此外，还可以把启动过程绘制成 SVG 图表供你审阅（用 GNOME 的图片预览或 Chrome 浏览器都可以打开），这个图表中你还可以观察到是否有启动慢的组件影响到了依赖它的组件的启动：

```
systemd-analyze plot > plot.svg
```

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 12 将npm的注册表源设置为国内的镜像

国内用户，建议将npm的注册表源设置为国内的镜像，可以大幅提升安装速度。

-   淘宝npm镜像

>   搜索地址：<http://npm.taobao.org/>
>
>   registry地址：<http://registry.npm.taobao.org/>

-   cnpmjs镜像

>   搜索地址：<http://cnpmjs.org/>
>
>   registry地址：<http://r.cnpmjs.org/>

-   临时使用

```
npm --registry https://registry.npm.taobao.org install express
```

-   持久使用

```
npm config set registry https://registry.npm.taobao.org
```

-   配置后可通过下面方式来验证是否成功
    `npm config get registry`
    或
    `npm info express`

-   通过cnpm(*可能需要加上sudo*)

    `npm install -g cnpm --registry=https://registry.npm.taobao.org`

-   使用
    `cnpm install express`

我使用的是cnpm.如下图:

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111158407-1723419260.png)

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 13 问题与解决



### 13.1 安装中遇到的问题

-   安装时一直停在“正在加载位置数据”

    解决办法：先把网络连接都断开，再启动安装，等地图位置加载完成后，再联网继续安装。



### 13.2 警告：xxx本地比xxx的版本更新

例如，加入archlinuxcn中文社区库后，执行sudo pacman -Syu升级系统后，出现如下问题：

```bash
1......
2警告：cower：本地 (18-2) 比 extra 的版本更新 (18-1)
3警告：inxi：本地 (3.0.29-1) 比 community 的版本更新 (3.0.28-1)
4警告：lib32-qt4：本地 (4.8.7-14) 比 multilib 的版本更新 (4.8.7-13)
5警告：libxpresent：本地 (1.0.0+3+g9d31d21-1) 比 extra 的版本更新 (1.0.0+2+gdd6771c-1)
6警告：package-query：本地 (1.9-3) 比 extra 的版本更新 (1.9-2)
7......
```

#### 13.2.1 解决办法

该问题一般出现在：启用了多个镜像（比如同时使用manjaro官方库和archlinuxcn中文社区库），或者刚切换了镜像，然后执行升级系统命令。

该问题可以忽略，因为archlinuxcn中文社区库里面的版本要比manjaro官方库里面的版本更新，升级后本地的版本就是使用archlinuxcn中文社区库里面的最新版本。

例如：

```bash
1$ pacman -Ss cower
2extra/cower 18-1 [已安装: 18-2]
3    A simple AUR agent with a pretentious name
4archlinuxcn/cower 18-2 [已安装]
5    A simple AUR agent with a pretentious name
```

当然，也可以给软件包降级：

-   使用pacman的临时文件（安装本地包）降级

    如果一个新包刚刚被安装并且没有删除[pacman cache](https://wiki.archlinux.org/index.php/Pacman#Cleaning_the_package_cache),你可以在`/var/cache/pacman/pkg/`中找到较早版本. 安装替换现有的版本.

    [pacman](https://wiki.archlinux.org/index.php/Pacman)会处理依赖包但不会处理依赖库的版本冲突。如果一个其依赖库因该包降级需要降级，你需要手动降级这些包。

    `pacman -U /var/cache/pacman/pkg/package-old_version.pkg.tar.xz`

-   使用远程包（安装远程包）降级

    `pacman -U http://www.example.com/repo/package-old_version.pkg.tar.xz`



### 13.3 aria2c下载xxx.db.sig出现错误



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看aria2c下载xxx.db.sig错误的详细内容</summary></details>



#### 13.3.1 解决办法

xxx.db.sig 缺失是 database 的签名缺失，这是正常的，现在都只验证 package 的签名，database 都不签名了。

在官方仓库和archlinuxcn中文社区库里已经没有xxx.db.sig文件了，所以当然下载不到。



### 13.4 错误：无法注册 ‘archlinuxcn’ 数据库 (数据库已登记)

```bash
1......
2error: could not register 'archlinuxcn' database (database already registered)
3error: could not register 'archlinuxcn' database (database already registered)
4error: could not register 'archlinuxcn' database (database already registered)
5could not register 'archlinuxcn' database (database already registered)
6错误：无法注册 'archlinuxcn' 数据库 (数据库已登记)
7错误：无法注册 'archlinuxcn' 数据库 (数据库已登记)
8错误：无法注册 'archlinuxcn' 数据库 (数据库已登记)
9......
```

该问题一般出现在添加archlinuxcn中文社区库的时候添加错文件了，应该是在这个文件“==/etc/pacman.conf==”后面添加archlinuxcn中文社区库，而不是在这个“/etc/pacman.d/mirrorlist”文件后添加。

![img](https://img2018.cnblogs.com/blog/1548353/201812/1548353-20181215111136319-520114191.png)

[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 附录I：/etc/pacman.conf

------



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看/etc/pacman.conf的详细内容</summary></details>



[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 附录II：/etc/makepkg.conf

------



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看/etc/makepkg.conf的详细内容</summary></details>



[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 附录III：/etc/pacman.d/mirrorlist

------



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看/etc/pacman.d/mirrorlist的详细内容</summary></details>



[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#_labelTop)

## 附录IV：.zshrc

------



<details style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;"><summary style="margin: 0px; padding: 0px; color: inherit; line-height: inherit; font-size: inherit;">点击查看.zshrc的详细内容</summary></details>





分类: [Linux](https://www.cnblogs.com/elinuxboy/category/1350873.html)



[好文要顶](javascript:void(0);) [关注我](javascript:void(0);) [收藏该文](javascript:void(0);) [![img](https://common.cnblogs.com/images/icon_weibo_24.png)](javascript:void(0);) [![img](https://common.cnblogs.com/images/wechat.png)](javascript:void(0);)

![img](https://pic.cnblogs.com/face/1548353/20181127204200.png)

[elinuxboy](https://home.cnblogs.com/u/elinuxboy/)
[关注 - 0](https://home.cnblogs.com/u/elinuxboy/followees)
[粉丝 - 4](https://home.cnblogs.com/u/elinuxboy/followers)





[+加关注](javascript:void(0);)

0

0







[« ](https://www.cnblogs.com/elinuxboy/p/10030023.html)上一篇：[数据结构与算法——学习整理记录](https://www.cnblogs.com/elinuxboy/p/10030023.html)
[» ](https://www.cnblogs.com/elinuxboy/p/10136485.html)下一篇：[单链表 C语言 学习记录](https://www.cnblogs.com/elinuxboy/p/10136485.html)

posted @ 2018-12-15 16:56 [elinuxboy](https://www.cnblogs.com/elinuxboy/) 阅读(5779) 评论(1) [编辑](https://i.cnblogs.com/EditPosts.aspx?postid=10123877) [收藏](https://www.cnblogs.com/elinuxboy/p/10123877.html#)





评论列表



  

\#1楼



 

2019-04-13 20:19

 

丿之夕

 

 

太用心了吧，厉害

[支持(0)](javascript:void(0);)[反对(0)](javascript:void(0);)







[刷新评论](javascript:void(0);)[刷新页面](https://www.cnblogs.com/elinuxboy/p/10123877.html#)[返回顶部](https://www.cnblogs.com/elinuxboy/p/10123877.html#top)

注册用户登录后才能发表评论，请 [登录](javascript:void(0);) 或 [注册](javascript:void(0);)，[访问](http://www.cnblogs.com/)网站首页。



[【推荐】超50万C++/C#源码: 大型实时仿真组态图形源码](http://www.ucancode.com/index.htm)
[【前端】SpreadJS表格控件，可嵌入系统开发的在线Excel](https://www.grapecity.com.cn/developer/spreadjs?utm_source=cnblogs&utm_medium=blogpage&utm_term=bottom&utm_content=SpreadJS&utm_campaign=community)
[【培训】阿里P8面试官：什么样的人能进阿里](https://ke.qq.com/adActivity.html?name=xiangxueketang2)
[【推荐】程序员问答平台，解决您开发中遇到的技术难题](https://q.cnblogs.com/)



**相关博文：**
· [Linux踩坑记录](https://www.cnblogs.com/cunyusup/p/9265019.html)
· [webpack踩坑记录（一）](https://www.cnblogs.com/noob-xw/p/9740434.html)
· [mongodb安装配置启动踩的坑](https://www.cnblogs.com/adhehe/p/10107983.html)
· [ABP Zero项目入门踩坑](https://www.cnblogs.com/ldybyz/p/8441084.html)
· [maven的pom配置详解](https://www.cnblogs.com/tanghaoran-blog/p/10429329.html)



### 公告

昵称：

elinuxboy

园龄：

6个月

粉丝：

4

关注：

0

[+加关注](javascript:void(0);)

| [<](javascript:void(0);)2019年6月[>](javascript:void(0);) |      |      |      |      |      |      |
| --------------------------------------------------------- | ---- | ---- | ---- | ---- | ---- | ---- |
| 日                                                        | 一   | 二   | 三   | 四   | 五   | 六   |
| 26                                                        | 27   | 28   | 29   | 30   | 31   | 1    |
| 2                                                         | 3    | 4    | 5    | 6    | 7    | 8    |
| 9                                                         | 10   | 11   | 12   | 13   | 14   | 15   |
| 16                                                        | 17   | 18   | 19   | 20   | 21   | 22   |
| 23                                                        | 24   | 25   | 26   | 27   | 28   | 29   |
| 30                                                        | 1    | 2    | 3    | 4    | 5    | 6    |

### 搜索

 

 



### 我的标签

-   [复杂度](https://www.cnblogs.com/elinuxboy/tag/%E5%A4%8D%E6%9D%82%E5%BA%A6/)(1)
-   [数据结构](https://www.cnblogs.com/elinuxboy/tag/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84/)(1)
-   [算法](https://www.cnblogs.com/elinuxboy/tag/%E7%AE%97%E6%B3%95/)(1)

### 随笔分类

-   [Linux(1)](https://www.cnblogs.com/elinuxboy/category/1350873.html)
-   [数据结构与算法学习分享(1)](https://www.cnblogs.com/elinuxboy/category/1350852.html)

### 随笔档案

-   [2018年12月 (3)](https://www.cnblogs.com/elinuxboy/archive/2018/12.html)
-   [2018年11月 (1)](https://www.cnblogs.com/elinuxboy/archive/2018/11.html)

### 最新评论

-   [1. Re:manjaro xfce 18.0 踩坑记录](https://www.cnblogs.com/elinuxboy/p/10123877.html#4230390)
-   太用心了吧，厉害
-   --丿之夕
-   [2. Re:数据结构与算法——学习整理记录](https://www.cnblogs.com/elinuxboy/p/10030023.html#4141141)
-   虽然没看懂，感觉很高深。佩服！
-   --赔钱农民工

### 阅读排行榜

-   [1. manjaro xfce 18.0 踩坑记录(5779)](https://www.cnblogs.com/elinuxboy/p/10123877.html)
-   [2. Linux mint xfce 19 使用记录(300)](https://www.cnblogs.com/elinuxboy/p/10136747.html)
-   [3. 数据结构与算法——学习整理记录(145)](https://www.cnblogs.com/elinuxboy/p/10030023.html)
-   [4. 单链表 C语言 学习记录(140)](https://www.cnblogs.com/elinuxboy/p/10136485.html)

### 评论排行榜

-   [1. manjaro xfce 18.0 踩坑记录(1)](https://www.cnblogs.com/elinuxboy/p/10123877.html)
-   [2. 数据结构与算法——学习整理记录(1)](https://www.cnblogs.com/elinuxboy/p/10030023.html)







Copyright ©2019 elinuxboy



## 目录导航