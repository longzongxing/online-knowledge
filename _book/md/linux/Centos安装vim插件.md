# Centos 7 安装vim插件

## VIM基本配置

~/.vimrc

```sh
"winpos 5 5          " 设定窗口位置  
"
""set lines=40 columns=155    " 设定窗口大小  

"set nu              " 显示行号  
"
"set go=             " 不要图形按钮  
"
""color asmanian2     " 设置背景主题  

set guifont=Courier_New:h10:cANSI   " 设置字体  

"syntax on           " 语法高亮  
"
"autocmd InsertLeave * se nocul  " 用浅色高亮当前行  
"
"autocmd InsertEnter * se cul    " 用浅色高亮当前行  
"
""set ruler           " 显示标尺  

set showcmd         " 输入的命令显示出来，看的清楚些  

"set cmdheight=1     " 命令行（在状态行下）的高度，设置为1  
"
""set whichwrap+=<,>,h,l   " 允许backspace和光标键跨越行边界(不建议)  

"set scrolloff=3     " 光标移动到buffer的顶部和底部时保持3行距离  
"
"set novisualbell    " 不要闪烁(不明白)  
"
"set statusline=%F%m%r%h%w\ [FORMAT=%{&ff}]\ [TYPE=%Y]\ [POS=%l,%v][%p%%]\
"%{strftime(\"%d/%m/%y\ -\ %H:%M\")}   "状态行显示的内容  
"
"set laststatus=1    " 启动显示状态行(1),总是显示状态行(2)  
"
"set foldenable      " 允许折叠  
"
"set foldmethod=manual   " 手动折叠  
"
""set background=dark "背景使用黑色 

set nocompatible  "去掉讨厌的有关vi一致性模式，避免以前版本的一些bug和局限  

" 显示中文帮助
"
" if version >= 603
"
"     set helplang=cn
"
"         set encoding=utf-8
"
"         endif
"
"         " 设置配色方案
"
"         "colorscheme murphy
"
"         "字体 
"
"         "if (has("gui_running")) 
"
"         "   set guifont=Bitstream\ Vera\ Sans\ Mono\ 10 
"
"         "endif 
"
"
"          
"          set fencs=utf-8,ucs-bom,shift-jis,gb18030,gbk,gb2312,cp936
"
"          set termencoding=utf-8
"
"          set encoding=utf-8
"
"          set fileencodings=ucs-bom,utf-8,cp936
"
"          set fileencoding=utf-8
"
"
"



nmap <leader>w :w!<cr>

nmap <leader>f :find<cr>



" 映射全选+复制 ctrl+a
"
" map <C-A> ggVGY
"
" map! <C-A> <Esc>ggVGY
"
" map <F12> gg=G
"
" " 选中状态下 Ctrl+c 复制
"
" vmap <C-c> "+y
"
" "去空行  
"
 nnoremap <F2> :g/^\s*$/d<CR> 
"
" "比较文件  
"
" nnoremap <C-F2> :vert diffsplit 
"
" "新建标签  
"
" map <M-F2> :tabnew<CR>  
"
" "列出当前目录文件  
"
" map <F3> :tabnew .<CR>  
"
" "打开树状文件目录  
"
" map <C-F3> \be  
"
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" 设置当文件被改动时自动载入
"
" set autoread
"
" " quickfix模式
"
" autocmd FileType c,cpp map <buffer> <leader><space> :w<cr>:make<cr>
"
" "代码补全 
"
 set completeopt=preview,menu 
"
" "允许插件  
"
" filetype plugin on
"
" "共享剪贴板  
"
" set clipboard+=unnamed 
"
" "从不备份  
"
" set nobackup
"
" "make 运行
"
 :set makeprg=g++\ -Wall\ \ %
"
" "自动保存
"
" set autowrite
"
" set ruler                   " 打开状态栏标尺
"
" set cursorline              " 突出显示当前行
"
" set magic                   " 设置魔术
"
" set guioptions-=T           " 隐藏工具栏
"
" set guioptions-=m           " 隐藏菜单栏
"
" "set statusline=\ %<%F[%1*%M%*%n%R%H]%=\ %y\ %0(%{&fileformat}\
" %{&encoding}\ %c:%l/%L%)\
"
" " 设置在状态行显示的信息
"
" set foldcolumn=0
"
" set foldmethod=indent 
"
" set foldlevel=3 
"
" set foldenable              " 开始折叠
"
" " 不要使用vi的键盘模式，而是vim自己的
"
" set nocompatible
"
" " 语法高亮
"
 set syntax=on
"
" " 去掉输入错误的提示声音
"
" set noeb
"
" " 在处理未保存或只读文件的时候，弹出确认
"
" set confirm
"
" " 自动缩进
"
" set autoindent
"
" set cindent
"
" " Tab键的宽度
"
 set tabstop=4
"
" " 统一缩进为4
"
" set softtabstop=4
"
" set shiftwidth=4
"
" " 不要用空格代替制表符
"
" set noexpandtab
"
" " 在行和段开始处使用制表符
"
" set smarttab
"
" " 显示行号
"
 set number
"
" " 历史记录数
"
 set history=1000
"
" "禁止生成临时文件
"
" set nobackup
"
" set noswapfile
"
" "搜索忽略大小写
"
 set ignorecase
"
" "搜索逐字符高亮
"
 set hlsearch
"
 set incsearch
"
" "行内替换
"
" set gdefault
"
" "编码设置
"
 set enc=utf-8
"
 set fencs=utf-8,ucs-bom,shift-jis,gb18030,gbk,gb2312,cp936
"
" "语言设置
"
 set langmenu=zh_CN.UTF-8
"
 set helplang=cn
"
" " 我的状态行显示的内容（包括文件类型和解码）
"
" "set statusline=%F%m%r%h%w\ [FORMAT=%{&ff}]\ [TYPE=%Y]\ [POS=%l,%v][%p%%]\
" %{strftime(\"%d/%m/%y\ -\ %H:%M\")}
"
" "set statusline=[%F]%y%r%m%*%=[Line:%l/%L,Column:%c][%p%%]
"
" " 总是显示状态行
"
 set laststatus=2
"
" " 命令行（在状态行下）的高度，默认为1，这里是2
"
" set cmdheight=2
"
" " 侦测文件类型
"
" filetype on
"
" " 载入文件类型插件
"
" filetype plugin on
"
" " 为特定文件类型载入相关缩进文件
"
" filetype indent on
"
" " 保存全局变量
"
" set viminfo+=!
"
" " 带有如下符号的单词不要被换行分割
"
" set iskeyword+=_,$,@,%,#,-
"
" " 字符间插入的像素行数目
"
" set linespace=0
"
" " 增强模式中的命令行自动完成操作
"
" set wildmenu
"
" " 使回格键（backspace）正常处理indent, eol, start等
"
" set backspace=2
"
" " 允许backspace和光标键跨越行边界
"
" set whichwrap+=<,>,h,l
"
" " 可以在buffer的任何地方使用鼠标（类似office中在工作区双击鼠标定位）
"
 set mouse=a
"
 set selection=exclusive
"
 set selectmode=mouse,key
"
" " 通过使用: commands命令，告诉我们文件的哪一行被改变过
"
 set report=0
"
" " 在被分割的窗口间显示空白，便于阅读
"
" set fillchars=vert:\ ,stl:\ ,stlnc:\
"
" " 高亮显示匹配的括号
"
 set showmatch
"
" " 匹配括号高亮的时间（单位是十分之一秒）
"
 set matchtime=1
"
" " 光标移动到buffer的顶部和底部时保持3行距离
"
" set scrolloff=3
"
" " 为C程序提供自动缩进
"
" set smartindent
"
" " 高亮显示普通txt文件（需要txt.vim脚本）
"
 au BufRead,BufNewFile *  setfiletype txt
"
" "自动补全
"
 :inoremap ( ()<ESC>i
"
 :inoremap ) <c-r>=ClosePair(')')<CR>
"
 :inoremap { {<CR>}<ESC>O
"
 :inoremap } <c-r>=ClosePair('}')<CR>
"
 :inoremap [ []<ESC>i
"
 :inoremap ] <c-r>=ClosePair(']')<CR>

 :inoremap " ""<ESC>i
"
 :inoremap ' ''<ESC>i
"
 function! ClosePair(char)
     if getline('.')[col('.') - 1] == a:char
"
             return "\<Right>"
"
                 else
"
                         return a:char
"
                             endif

                             endfunction
"
                             filetype plugin indent on 
"
"                             "打开文件类型检测, 加了这句才可以用智能补全
"
                             set completeopt=longest,menu
"
"                             """""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" CTags的设定  
"
" """""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"
 let Tlist_Sort_Type = "name"    " 按照名称排序  
"
let Tlist_Use_Right_Window = 1  " 在右侧显示窗口  
"
 let Tlist_Compart_Format = 1    " 压缩方式  
"
 let Tlist_Exist_OnlyWindow = 1  "
" 如果只有一个buffer，kill窗口也kill掉buffer  
"
" let Tlist_File_Fold_Auto_Close = 0  " 不要关闭其他文件的tags  
"
" let Tlist_Enable_Fold_Column = 0    " 不要显示折叠树  
"
" autocmd FileType java set tags+=D:\tools\java\tags  
"
" "autocmd FileType h,cpp,cc,c set tags+=D:\tools\cpp\tags  
"
" "let Tlist_Show_One_File=1
" "不同时显示多个文件的tag，只显示当前文件的
"
" "设置tags  
"
"--ctags setting--

"
"
"
" """"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"
" "默认打开Taglist 
"
let Tlist_Auto_Open=1 
"
" """""""""""""""""""""""""""""" 
"
" " Tag list (ctags) 
"
" """""""""""""""""""""""""""""""" 
"
 let Tlist_Ctags_Cmd = '/usr/bin/ctags' 
"
 let Tlist_Show_One_File = 1 "不同时显示多个文件的tag，只显示当前文件的 
"
 let Tlist_Exit_OnlyWindow = 1 "如果taglist窗口是最后一个窗口，则退出vim 
"
 let Tlist_Use_Right_Window = 1 "在右侧窗口中显示taglist窗口
"
" " minibufexpl插件的一般设置

 let g:miniBufExplMapWindowNavVim = 1

 let g:miniBufExplMapWindowNavArrows = 1

 let g:miniBufExplMapCTabSwitchBufs = 1
 let g:miniBufExplModSelTarget = 1
```



## 1.安装VIM插件

```sh
# 1.安装VIM管理插件
git clone https://github.com/egalpin/apt-vim.git
cd apt-vim
sudo ./apt-vim init
# 将~/.vimpkg/bin加入PATH（~/.vimpkg/bin即所有vim插件依赖），即将
export PATH=$PATH:~/.vimpkg/bin
# 最后在.vimrc添加如下代码：
execute pathogen#infect()
call pathogen#helptags()
# 执行
apt-vim install -y

# 2.用法
 apt-vim <mode> [options] [URLs]
# 其中mode可以是init、install、list、add、remove、delete、update
# ~/.vimpkg/vim_config.json中存放着所有在用的插件配置。

apt-vim init
apt-vim install [options] [URLs]
apt-vim list
apt-vim add [options] URLs
apt-vim remove [options] URLs
apt-vim remove [options] URLs
apt-vim update [options] [URLs]

```

## 2.安装nerdtree

```sh
# 通过apt-vim 安装
apt-vim install -y https://github.com/scrooloose/nerdtree.git
# .vimrc 添加
autocmd vimenter * NERDTree
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
```

## 3.安装nerdcommenter

功能：快速注释、解开注释

github地址

安装 ：通过Vundle ：Plugin ‘scrooloose/nerdcommenter’

使用：

使用：

```
使用：
1、 \cc 注释当前行和选中行
2、 \cn 没有发现和\cc有区别
3、 \c<空格> 如果被选区域有部分被注释，则对被选区域执行取消注释操作，其它情况执行反转注释操作
4、 \cm 对被选区域用一对注释符进行注释，前面的注释对每一行都会添加注释
5、 \ci 执行反转注释操作，选中区域注释部分取消注释，非注释部分添加注释
6、 \cs 添加性感的注释，代码开头介绍部分通常使用该注释
7、 \cy 添加注释，并复制被添加注释的部分
8、 \c$ 注释当前光标到改行结尾的内容
9、 \cA 跳转到该行结尾添加注释，并进入编辑模式
10、\ca 转换注释的方式，比如： /**/和//
11、\cl \cb 左对齐和左右对其，左右对其主要针对/**/
12、\cu 取消注释
```



```sh

# .vimrc的配置
" Add spaces after comment delimiters by default
let g:NERDSpaceDelims = 1

let g:NERDCustomDelimiters = { 'c': { 'left': '/**','right': '*/' } }  "自定义注释符


let g:NERDDefaultAlign = 'left'             "左对齐 注释符
let g:NERDCompactSexyComs = 1      " 和上一个一起使用，多行注释 ,注释符全部都在行首

let g:NERDTrimTrailingWhitespace = 1    "uncomment的时候，修减行末的空格
```

## 3.安装YouCompleteMe

-   功能：自动补全
-   [github地址](https://github.com/Valloric/YouCompleteMe#full-installation-guide)

```sh
# 安装
apt-vim install -y https://github.com/Valloric/YouCompleteMe#full-installation-guide.git
# 使用
cd ~/.vim/YouCompleteMe/third_party/ycmd/.ycm_extra_conf.py
# 打开.ycm_extra_conf.py文件，在flags里面的最下面添加（如需要补全其他库，按照格式添加即可，注意后面 有逗号）
'-isystem',
    '/usr/include/c++/5.4.0',
    '-isystem',
    '/usr/include/x86_64-linux-gnu/c++',
    '-isystem',
    '/usr/include',
    
# 配置
vi .vimrc 
let g:ycm_global_ycm_extra_conf = '~/.vimrc/YouCompleteMe/third_party/ycm/.ycm_extra_conf.py'
```

```sh
# 使用git 安装
# 下载 （在 `～/.vim/bundle` 目录下）
$ git clone --recursive https://github.com/Valloric/YouCompleteMe.git
# 检查完整性（在 `～/.vim/bundle/YouCompleteMe` 目录下）
$ git submodule update --init --recursive

2. 下载安装最新版的 libclang
如果不需要 C 家族的语义化补全，则可跳过这一步
# apt-get install llvm-3.9 clang-3.9 libclang-3.9-dev libboost-all-dev
3. 编译构建 ycm_core 库
** 需要：cmake python3-dev**
YCM 的顶层目录或者说根目录应该是 ～/.vim/bundle/YouCompleteMe

创建一个目录放编译过程中产生的文件
$ mkdir ~/.ycm_build
$ cd ~/.ycm_build
生成 makefile
如果跳过第三步的话，则可以直接运行

$ cmake -G "Unix Makefiles" . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp
如果没有跳过第三步，说明需要 c 家族的语义化补全则需运行
$ cmake -G "Unix Makefiles" -DUSE_SYSTEM_BOOST=ON DUSE_SYSTEM_LIBCLANG=ON . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp
$ cmake -G "Unix Makefiles" -DUSE_SYSTEM_BOOST=ON -DUSE_SYSTEM_LIBCLANG=ON . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp


```

## 4.安装ctags
功能：函数、变量的跳转
安装：
  这个并不是插件，而是可执行程序，是用来对代码建索引，方便查找的，有些Linux版本是自带ctags的，如果没有，按如下方式安装:sudo apt-get install ctags

生成ags：
递归当前目录中所有文件tags：ctags -R
特定的文件：ctags *.c *.h
系统库tags：ctags -I __THROW --file-scope=yes --langmap=c:+.h --languages=c,c++ --links=yes --c-kinds=+p --fields=+S -R -f ~/.vim/systags /usr/include /usr/local/include
C++文件tags：ctags -I __THROW -I __THROWNL -I __attribute_pure__ -I __nonnull -I __attribute__ -R --c++-kinds=+px --fields=+iaS --extra=+q

```
    set tags+=~/.vim/systags
#操作：
Ctrl+]：跳到定义处
Ctrl+o/t：跳回上次处
:tn 下一个
:tp 上一个
:ts 列出所有
```

## 5.vim-autoformat

   功能：格式化代码
github地址
安装 ：通过Vundle ：Plugin ‘Chiel92/vim-autoformat’
使用
使用之前你得下载自动格式的工具：对于C C++可以使用clang-format(需要安装：sudo apt-get install clang-format)
在自己工程根目录下，建立.clang-format文件，在里面自定义格式(具体查看官网)

---------------------
