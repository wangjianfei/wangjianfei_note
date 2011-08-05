# vim

##vim 命令的基本模式：  

	Command = operator + number + motion
		d(elete)  1,2
		y(ank)             gg+G

对 vim的命令的基本操作主要包括以上三个部分

##vim基本命令：

###插入模式

vim中查单词：ctrl + x + k

### 普通模式：

r and R 都可以用来替换字符  r 替换一个字符   R 替换多个字符

undo 是 u键  撤销上次操作

redo  是 ctrl+r 撤销超过 返回一步

### 模行模式：

:vnew file 打开两个窗口， 纵向分成两部分

:new  file 横向分成两部分 

:!命令  可以执行和bash里面一样的命令

打开多个文件时的一些操作：

:e file.c  在当前文件下打开另一个当前目录下存在或者不存在的文件

:ls 看大开了几个文件

:bn 看下一个文件

:bp 看上一个文件

:bd 关闭当前文件  首先要保存

:wa 保存所有

##vim的tip:

在vim中要粘贴  必须进入插入模式

打开vim文件时有错误  可能是存在一个.swp文件 解决方法是将其删除 造成原因很多

如：异常关闭、或者在另一个bash里面打开等

vim  按‘V’则可以进入可视行模式 把光标放在你要选中的内容的第一行或者最后一行

然后按‘j’和‘k’可选中要删除的行,按‘d’即可删除,按‘y’则可复制选中的内容，按‘p’

则可粘贴删除和复制的内容       再次按‘V’则可退出可视行模式


在可视行下选中，按‘>’'<'则可以进行整体缩进
   则可以进行整体缩进 
vim .vimrc  里面可以写上自己对vim的设置  可以永久生效

在vimrc中：ctrl + x + f 为补齐路径

vimtutor 是查看vim的基本命令信息

key map  -------->是映射的意思

exampls:在vim文件写信时，查询单词拼写错误 末行模式:set spell

命令比较繁琐：在vimrc里面设置：map ,ss :set spell<\cr>

回车：cariage return 'r'   换行 '\n'

unix下 '\n'='\n'+'\r'  windows   '\n'='\n'   注意文件格式匹配问题

同时 设置imap jj   `<esc>`  在插入模式时退出

注意：__`<esc>`__  要加单引号  否则不能显示  系统把默认为转义字符

写程序时的vim tip：在写vim时，在普通模式时

:w 保存文件  必须首先要做

:sh 在当前vim上打开一个bash

ctrl d 或者exit 则可以关闭当前的bash,进入vim编辑器

其优点是：光标在vim中的位置不会变  较大程序时比较方便


vim的帮助

普通模式下 :h +命令  如果是插入时的命令  :h i_ctrl-t 来实现查询

#两种网页编写语言：

##markdown

http://happypeter.github.com/LGCB/book/toy_markdown.html  是peter老师的笔记

里面的链接可以得到学习markdown的资料

word 两边都加上两个'__' 则可以将 word 变成粗体

##html study

http://www.w3schools.com/    学习 html语言  

其实markdown语言也是转换成html语言来实现网页编写的

markdown的后缀名是.md

html语言的后缀名是.html

终端中命令： markdown file.md > file.html 

firefox file.html


# git    管理软件的软件

## install

sudo apt-get install git-core 安装 git  管理软件的软件

sudo apt-get install tig     安装  tig   查看软件修改的地方


##git command

git checkout 哈希值  可以打开那个版本 tig时也就只显示这个版本以前的版本

git checkout 哈希值 -b  分支名  创建一个分支 名字为“分支名”

git checkout master 回到主分支

git branch   查看分支

要删除某个分支  git checkout  到其它分支  才能删除此分支

git branch -D 分支名

重命名 mv main.c hello.c  git add . 可以实现重命名

git mv main.c hello.c  也行

delete a Repositories(仓库)

Dashboard -> 进入要删除的仓库 -> Admin -> 到最下面选择Delete this repository

git rm file  delete the file I do not need  git commit -a -m  "git push"

git pull  下载最新的笔记  

git diff 查看自己现在wangjianfei.md 和.git 里面的wangjianfei.md的区别 

git reset --hard HEAD 将自己的wangjianfei.md还原成.git 里

 面的wangjianfei.md

如果已经将垃圾修改生成版本  则可以通过git reset --hard HEAD^ 得到上一个版本

如果已将垃圾push上去，则可以通过git revert 删除上次修改，生成和它上上个版本

一样的又一个版本

.gitconfig 是git的配置文件

vim  .gitconfig 是打开git的配置文件 

##git basics   git 的基本操作步骤

1. first create a dir

        mkdir  folder（文件夹）

2. now you MUST cd to this dir

        cd folder

3. initializing this git dir

        git init  git初始化

        ls -a   now you can see a `.git` in this dir

4. now create a file

        vim file.c

5. let git knows about this file

        git add file.c

        如果有多个文件跟踪方式如下：

        git add .

6. create the first version

git commit -a -m "my first version"

-a :是all的意思  即跟踪所有修改地方

-m :是message的意思    后面跟上修改留言
      
    当message的信息较多时，我们可以执行 git commit -a 进入一个编辑器，
第一行是标题 隔一行开始写message的信息

开始时首先应该在 .gitconfig 里面添加[core]    editor = vim

将编辑器设置成vim
    

tig查看版本

ref:    http://progit.org/

通过最下面的 chinese 可以转换成中文

video: search "linus git" at youku.com 纯英语

#github账户申请

##github的申请：

    打开主页，点击“plans,pricing and signup”，

              再点击“creat a free account”
    
    再添写基本的个人信息 上交即可

##ssh申请上传过程：

   1、cd  回到主目录

   2、ssh-keygen  点击直到出现图框
    
   3、ls -a  cd .ssh  vim id_rsa.pub 复制 但开始和最后绝不能有空格 否则不能成功

   4、打开 github 的主页：  点击 account setting
 
                          再点击 SSH Public keys

            则可以上传公共密钥

##Global setup:

  Set up git

  git config --global user.name "Your Name" 在修改内容中显示自己的帐户名

  git config --global user.email 214653406@qq.com  在修改内容中显示自己的邮箱
        

##Next steps:

  mkdir wangjianfei_note

  cd wangjianfei_note

  git init

  touch README

  git add README

  git commit -m 'first commit'

  git remote add origin git@github.com:wangjianfei/wangjianfei_note.git

   origin 是指的一个别名  就是后面的网址

  git push -u origin  __master__  是主仓库的意思
      

##Existing Git Repo?

  cd existing_git_repo 创建一个新的仓库

  git remote add origin git@github.com:wangjianfei/wangjianfei_note.git

           用orign代替后面的网址   在一台机器上用一次以后就ok了

  git push -u origin master

           只是第一次这么些  以后只是 git push 就ok  了
      

##Importing a Subversion Repo?

  Click here
      

##When you are done:

  Continue


#linux   基本知识

##linux basics

  Linux is OS(operating system)

  OS as linus see it:

  OS is nothing but the kernel.

  Linux is nothing but the kernel.

  ubuntu is Linux + 1000 app.

  OS as MS see it:

  OS is kernel + desktop env.

  path   : 绝对路径: start with /

           相对路径: start with .

  shell prompt: peter@cow:~/tg-note$

                user@machinename:currentWorkingDirectory(folder)$

  shell is a commandline interpreter 是一个命令解释器

  bash  is a kind of shell

  bash的配置文件 .bashrc alias 取别名的意思在.bashrc里面 可以通过

  alias aaa='sudo  apt-get install'  来命名   以便简化命令

##linux basic command  自己掌握

dpkg -l 查看所装插件在那里，并且有那些文件

while are you ?

which + folder 查看命令装在哪里

locate + 部分关键字  定位在哪里 locate 有个数据库 是定时刷新的 不是实时刷新

作整个系统查询非常方便   但只能查找老文件    刚刚建立的文件需要更新 

sudo updatedb ---->更新数据库

find + 目录 则列出所有的内部文件  |---- >为管道符  是将前面的输出作为后面的输入

find + 目录|grep 部分关键字  可以查出所要求的   

ps aux ---> 类似与windows下的任务管理器  ps aux | grep folder 打开目标进程

kill+进程号 就是关闭  kill -9 + 进程号   强行关闭

xxx 是peter老师编写的命令  

首先从 github 中git clone hen  选择打开search ，打开curse , 根据README安装

xxx   则可以使用

xxx + 部分关键字  则可以显示要查询的信息  按“e”可以查看  shift zz  退出

xxx 主要用在项目中

source folder 是让bash重读该文件

diff: 
       
diff -u file.c file1.c   显示两者的不同

diff -u  file.c file1.c  > file.diff  生成差异文件file.diff

patch file.c < file.diff    生成新文件file.c=flie1.c

patch -R file.c < file.diff   还原成源文件

  wget  加上网址可以对其进行下载   写上 -r  写上总的网址全部下载

  totem 加上文件名可以对其进行播放
 
ifconfig 查看电脑的IP地址

##linux command tips

   Clear screen : Ctrl-l  清屏

   Copy and Paste: select -> middle button 复制粘贴

   按方向键即可选择以前用过的命令

   ctrl shift t 可以打开另一个bash

   ctrl pgUp 看上一个bash   ctrl pgDn 看下一个bash
  
   ctrl d  关闭当前bash     在command line write 'exit'

   安装插件的基本格式：sudo apt-get install 插件名 

   卸载插件的基本格式：sudo apt-get remove --purge folder
   
   或者 sudo apt-get purge folder

   下载资源来源： cd /etc/apt ---> sources.list 
 

#gcc basic knowledge 编译器基本知识

   gcc -Wall W是指warning 显示警告

             a是指all     显示所有

   linux main的返回值默认是0

   echo $? 是查看函数的返回值

   ldd 查看函数链接的库

   gcc -l+链接库的名字     标准库的链接在平时编译时省略  而不是不链接

   写程序要考虑硬件则是：低级语言

   写程序不考虑硬件则是：高级语言

#CC language 程序 基本知识

1、在程序中，出现循环次数时，最好采用宏定义，以方便修改  

当用vim编写时,在插入模式下 Ctrl n   可以补齐字符串  It will search

 current file and include files

2、coding style  代码形式
   
   推荐用4个空格来缩进  不允许tab和空格混合使用

   gitbub 中搜索peter—vim，可以得到peter老师的vim配置

   ctrl+t 向后缩进   ctrl+d 向前缩进
 
3、怎么读程序：

首先装一个插件: sudo apt-get install ctags

在工程中现执行  ctags folder   生成tags文件

读程序时 光标放在函数声明处或者定义处：

在vim 中，光标放在接口上，按‘K’,则可查找来源

ctrl+]看函数定义  ctrl+t 返回到刚才光标所在的位置

4、(2011.07.27)按位与、按位或、按位取反、按位异或

int--->char时，只是把整型的低八位给了字符型，当为正数时，正确；当为负数时，给

的是补码，要转换成真实的数值

char---->int , int的高位用char的最高符号位填补，得到的是int的补码，在转换成真实

的数值

在输入负数时，不要用十六进制，它把十六进制直接作为补码，计算结果会出错

5、(2011.07.28) switch 是选择入口的语句  进入语句只有遇到break才停止

每个子函数在执行时都会分配一个栈空间，执行完程序时，释放空间 实参--->形参

形参不传值给实参

在一个函数中有多个数值类型，当它们进行计算时 ，占用空间小的向占用空间大的转换，

    int a = 5;

    int b = 6;

    double c = a + b;

计算时，先把a、b转换成double型 再进行计算 double型一般不进行比较大小 因为有精度

注意int型和unsigned int 进行计算时，把int型转换成unsigned int型

当程序出现问题时，排错顺序：自己的程序  编译器  硬件出现问题

指针 是 存储地址的变量 ； 指针指向某个变量，也就是把变量地址给指针

sizeof is a key word ,sizeof(int)可以查看int型占几个变量

6、(2011.07.29)C语言不检查边界，字符串是以'\0'结束 ，字符数组可以没有'\0',字

符数组放字符串时，比字符串长度要大一，只有在定义时才可以直接把字符串赋值给字

符数组

有关状态机的编程思想，李老师讲的一些东西，主要是在编程是时设置状态变量 ，

根据不同的状态执行不同的命令。

7、（2011.07.30）程序员对数学水平的要求是：初等数学水平要求，也就是高中 ，

srand(time(NULL)),种一种子，也就是采一个时间点，rand() 产生一个随机数 ，

它们属于stdlib和time库，用man 可以查看

getchar() 是单个标准字符输入，在程序输出时，可以对其控制

8、（2011.07.31） 函数的递归调用，即自己调用自己，例程序：汉诺塔、求阶乘、

快速查找（重在理解快速查找的思想）

%p 是打印地址的格式：printf("%p\n" ,&a);  地址符&不可以省略

二维数组中的一些与指针有关的东西：array[][],是一个二维数组 ，

array = &array[0] = array[0] = &array[0][0]

9、(2011.08.01) 在一开始定义指针时，不知道给它赋什么值时，给它赋NULL，不

要不赋值，如果指针只在一个非常重要的地方，一不小心改变了其值，可能会造成

严重的后果 ，甚至整个程序崩溃

有关结构体的一些基本知识
                            
    struct date
    {
      int a ;
      int b ;
      struct date *ptr ;
    };

不分配任何存储空间 注意最后的';'不要丢了

结构体不能包含自己，结构体是否能包含仅限与它是否能确定大小

typedef 是定义类型：typedef strcut date date   下面就可以用date定义结构体

%-5d 是左对齐的意思 比较以下：%-5d 和%5d 就一目了然了

malloc(sizeof(struct date)); 开辟一个存放这种结构体堆空间；malloc函数用完了，

必须用free()释放，不然会造成内存泄漏

在函数调用中 ，函数执行结束 ，内存释放 ，但堆空间不释放

perror()打印出错误原因 ；为了区分是那个错误，经常在括号里写上写上一个字符串，

如perror("a_node")等 ，先打印字符串，再打印错误

exit();是一个终止进程的的函数，执行后可以终止进程

const 定义的变量值不能修改

const chat *p 指的是*p的内容不能修改 ，并不是指针不能改

char * const p  指的是p不能修改

static 可以修饰变量 也可以修饰函数

static int count 定义全局变量时，只有本文件可见

static int count 定义局部变量时，只有本函数可用，单调用结束后不释放，下次

调用时，上次的值让然存在

extern int count 声明count是一个已定义的外部变量


# tar 

unzip folder.zip -d ~/.file  是解压folder.zip 到主目录下的.file文件

http://www.happypeter.org/posts/10

# ref 两本学习参考书

http://happypeter.github.com/LGCB/

http://billie66.github.com/TLCL/book/

http://media.happypeter.org/  一些参考视频

## some of my favorite sites

http://www.linfo.org/

http://www.wikipedia.org/

http://news.ycombinator.com/news


# 个人学习

##ubuntu 的安装问题

一个'/'区 一个swap 固定的  虚拟内存

另一个 再加一个home的分区,以便重装系统时不删除自己的东西

##有关局域网的一些小知识：

常见端口地址：ftp:27  http:80   ssh:

linux 用ssh

成为服务器断要装 sudo apt-get install openssh-server

成为客户端要装 ssh-client

在bash里输入要进入的电脑的example：ssh peter@192.168.1.17

输入密码

sudo services ssh stop 关闭ssh服务

sudo services ssh start 打开ssh服务

从别人电脑上拷贝东西，在自己的电脑上：scp peter@192.168.1.17:~/file(文件路径) .

services ssh status 看服务状态

## 常用播放器

mplayer

## language

https://github.com/happypeter/job-akae/wiki

## translation

http://dict.youdao.com/

有道辞典  通用的IT辞典

http://learn.akae.cn/media/index.html

