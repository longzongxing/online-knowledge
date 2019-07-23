# Manajro 安装I3

## 1.I3简介



## 2.安装I3



## 3.I3快捷键



## 4.I3配置



## 5.常用工具详解

### 1.pacman

>   常用的操作
>
>   更新
>
>   pacman -Syu 对整个系统更新
>
>   安装
>
>   pacman -Sy 本地数据库与远程库同步
>
>   pacman -S 安装某个软件
>
>   删除
>
>   pacman -R 删除某个软件，保留安装依赖
>
>   pacman -Rs 删除软件，并清除没有的依赖关系软件
>
>   pacman -Rsc 删除软件，删除所有依赖这个软件的软件
>
>   搜索
>
>   pacman -Ss xxx 在仓库中搜索
>
>   pacman -Qs xxx 在已安装中搜索
>
>   pacman -Qi xx 查看安装包信息
>
>   

```
Pacman 是一个 软件包管理器, 作为 ArchLinux发行版的一部分. 它最早由 Arch Linux 的 Judd Vinet开发. Pacman 可以解决安装过程中的依赖问题，自动下载并且安装所有需要的软件包。Pacman包管理器是Arch Linux的一大亮点。它将一个简单的二进制包格式和易用的构建系统结合了起来。Pacman使得简单的管理与自定义软件包成为了可能，而不论他们来自于官方的Arch软件库或是用户自己创建的[zhangy@BlackGhost ~]$ pacman -h
用法:  pacman <操作> [...]
操作:
 pacman {-h --help}       //帮助
 pacman {-V --version}   //查看版本
 pacman {-D --database} <选项> <软件包>  //pacman管理数据库选项
 pacman {-Q --query}    [选项] [软件包]    //查询安装包
 pacman {-R --remove}   [选项] <软件包>  //删除安装包
 pacman {-S --sync}     [选项] [软件包]      //安装安装包
 pacman {-U --upgrade}  [选项] <文件>   //更新安装包

使用 'pacman {-h --help}' 及某个操作以查看可得的选项[zhangy@BlackGhost ~]$ pacman -D --help  
用法:  pacman {-D --database} <选项> <软件包>  
选项:  
 --asdeps         标记为非单独指定安装的软件包  
 --asexplicit     标记为单独指定安装的软件包  
 --config <路径>  指定另外的配置文件  
 --logfile <路径> 指定另外的日志文件  
 --noconfirm      不询问确认  
 --noprogressbar  下载文件时不显示进度条  
 --noscriptlet    不执行安装小脚本  
 -v, --verbose        循环执行  
 -- debug        显示除错信息  
 -r, --root <路径>    指定另外的安装根目录  
 -b, --dbpath <路径>  指定另外的数据库位置  
 --cachedir <目录> 指定另外的软件包缓存位置  
 --arch <架构>    设定另外的架构[zhangy@BlackGhost ~]$ pacman -Q --help  
用法:  pacman {-Q --query} [选项] [软件包]  
选项:  
 -c, --changelog      查看某软件包的更新日志  
 -d, --deps           列出所有作为依赖关系安装的软件包 [过滤器]  
 -e, --explicit       列出所有单独指定安装的软件包 [过滤器]  
 -g, --groups         查看某软件包组所属的所有软件包  
 -i, --info           查看软件包信息 (-ii 查看备份文件)  
 -k, --check          检查该软件包拥有的文件是否存在  
 -l, --list           列出被查询软件包的内容  
 -m, --foreign        列出没有在同步数据库时找到的已安装软件包 [过滤器]  
 -o, --owns <文件>     查询哪个软件包拥有  <文件>  
 -p, --file <软件包> 从某个软件包而不是数据库查询  
 -s, --search  搜寻符合指定字符串的已安装本地的软件包  
 -t, --unrequired     列出所有不被其他软件包要求的软件包 [过滤器]  
 -u, --upgrades       列出所有可升级的软件包 [过滤器]  
 -q, --quiet          在查询或搜索时显示较少的信息  
 --config <路径>  指定另外的配置文件  
 --logfile <路径> 指定另外的日志文件  
 --noconfirm      不询问确认  
 --noprogressbar  下载文件时不显示进度条  
 --noscriptlet    不执行安装小脚本  
 -v, --verbose        循环执行  
 -- debug        显示除错信息  
 -r, --root <路径>    指定另外的安装根目录  
 -b, --dbpath <路径>  指定另外的数据库位置  
 --cachedir <目录> 指定另外的软件包缓存位置  
 --arch <架构>    设定另外的架构 [zhangy@BlackGhost ~]$ pacman -R --help  
用法:  pacman {-R --remove} [选项] <软件包>  
选项:  
 -c, --cascade        删除软件包及所有的依赖于此的软件包  
 -d, --nodeps         略过依赖关系检查  
 -k, --dbonly         只删除数据库记录，不删除文件  
 -n, --nosave         同时删除配置文件  
 -s, --recursive      同时删除 (不会破坏其他软件包的) 依赖关系(-ss·也包括单独指定安装的依赖关系)  
 -u, --unneeded       同时删除不需要的 (且不会破坏其他软件包的) 依赖关系  
 --print          仅打印目标而不执行操作  
 --print-format <字符串>指定如何打印目标  
 --config <路径>  指定另外的配置文件  
 --logfile <路径> 指定另外的日志文件  
 --noconfirm      不询问确认  
 --noprogressbar  下载文件时不显示进度条  
 --noscriptlet    不执行安装小脚本  
 -v, --verbose        循环执行  
 -- debug        显示除错信息  
 -r, --root <路径>    指定另外的安装根目录  
 -b, --dbpath <路径>  指定另外的数据库位置  
 --cachedir <目录> 指定另外的软件包缓存位置  
 --arch <架构>    设定另外的架构  [zhangy@BlackGhost ~]$ pacman -S --help  
用法:  pacman {-S --sync} [选项] [软件包]  
选项:  
 --asdeps         作为非单独指定安装的软件包安装  
 --asexplicit     作为单独指定安装的软件包安装  
 -c, --clean          从缓存目录中删除旧软件包 (-cc 清除所有)  
 -d, --nodeps         略过依赖关系检查  
 -f,  -force          强制安装，覆盖存在冲突的文件  
 -g, --groups         查看某软件包组所属的所有软件包  
 -i, --info           查看软件包信息  
 -l, --list <软件库>    查看在该软件库中的软件包清单  
 -s, --search  按照指定字符串查询远端软件库  
 -u, --sysupgrade     升级所有已安装的软件包 (-uu 可启用降级)  
 -w, --downloadonly   下载但不安装/升级软件包  
 -y, --refresh        从服务器下载新的软件包数据库  
 --needed         不重新安装已经为最新的软件包  
 --ignore <软件包>   升级时忽略某个软件包 (可多次使用)  
 --ignoregroup <软件包组>升级时忽略某个软件包组 (可多次使用)  
 --print          仅打印目标而不执行操作  
 --print-format <字符串>指定如何打印目标  
 -q, --quiet          在查询或搜索时显示较少的信息  
 --config <路径>  指定另外的配置文件  
 --logfile <路径> 指定另外的日志文件  
 --noconfirm      不询问确认  
 --noprogressbar  下载文件时不显示进度条  
 --noscriptlet    不执行安装小脚本  
 -v, --verbose        循环执行  
 -- debug        显示除错信息  
 -r, --root <路径>    指定另外的安装根目录  
 -b, --dbpath <路径>  指定另外的数据库位置  
 --cachedir <目录> 指定另外的软件包缓存位置  
 --arch <架构>    设定另外的架构
[zhangy@BlackGhost ~]$ pacman -U --help  
用法:  pacman {-U --upgrade} [选项] <文件>  
选项:  
 --asdeps         作为非单独指定安装的软件包安装  
 --asexplicit     作为单独指定安装的软件包安装  
 -d, --nodeps         略过依赖关系检查  
 -f,  -force          强制安装，覆盖存在冲突的文件  
 -k, --dbonly         添加数据库记录，不安装或保持现存文件  
 --print          仅打印目标而不执行操作  
 --print-format <字符串> 指定如何打印目标  
 --config <路径>  指定另外的配置文件  
 --logfile <路径> 指定另外的日志文件  
 --noconfirm      不询问确认  
 --noprogressbar  下载文件时不显示进度条  
 --noscriptlet    不执行安装小脚本  
 -v, --verbose        循环执行  
 -- debug        显示除错信息  
 -r, --root <路径>    指定另外的安装根目录  
 -b, --dbpath <路径>  指定另外的数据库位置  
 --cachedir <目录> 指定另外的软件包缓存位置  
 --arch <架构>    设定另外的架构
```

```

```

