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

:sp 是行向分屏  ：vsp 是纵向分屏  用shift zz  退出

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

vim .vimrc  里面可以写上自己对vim的设置  可以永久生效

在vimrc中：ctrl + x + f 为补齐路径

vimtutor 是查看vim的基本命令信息

key map  -------->是映射的意思

exampls:在vim文件写信时，查询单词拼写错误 末行模式:set spell

命令比较繁琐：在vimrc里面设置：map ,ss :set spell<\cr>

map \<tab> :bn<\cr> 多个文件编辑时比较方便

回车：cariage return 'r'   换行 '\n'

unix下 '\n'='\n'+'\r'  windows   '\n'='\n'   注意文件格式匹配问题

同时 设置imap jj   `<esc>`  在插入模式时退出

注意：__`<esc>`__  要加单引号  否则不能显示  系统把默认为转义字符

写程序时的vim tip：在写vim时，在普通模式时

:w 保存文件  必须首先要做

:sh 在当前vim上打开一个bash

ctrl d 或者exit 则可以关闭当前的bash,进入vim编辑器

其优点是：光标在vim中的位置不会变  较大程序时比较方便

gg=G可以在vim中排版C程序

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

git checkout 哈值  可以打开那个版本 tig时也就只显示这个版本以前的版本

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

   gg=G可以在vim中排版C程序

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

man 可以分三部分：

man 1 命令  ：是指系统的命令

man 2 命令  ：是指系统的函数

man 3 命令  : 是标准的函数

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
  struct date *ptr;
};

不分配任何存储空间 注意最后的';'不要丢了

结构体不能包含自己，结构体是否能包含仅限与它是否能确定大小

typedef 是定义类型：typedef strcut date date   下面就可以用date定义结构体

%-5d 是左对齐的意思 比较以下：%-5d 和%5d 就一目了然了

malloc(sizeof(struct date)); 开辟一个存放这种结构体堆空间；malloc函数生命

周期是整个函数，作用域也是整个函数；malloc函数用完了，必须用free()释放，

不然会造成内存泄漏;如果进程完了，但没有关闭，也会造成内存泄漏

在函数调用中 ，函数执行结束 ，内存释放 ，但堆空间不释放

perror()打印出错误原因 ；为了区分是那个错误，经常在括号里写上写上一个字符串，

如perror("a_node")等 ，先打印字符串，再打印错误

exit();是一个终止进程的的函数，执行后可以终止进程

const 定义的变量值不能修改

const chat *p 指的是*p的内容不能修改 ，并不是指针不能改（p能改）

char * const p  指的是p不能修改

static 可以修饰变量 也可以修饰函数

static int count 定义全局变量时，只有本文件可见

static int count 定义局部变量时，只有本函数可用，单调用结束后不释放，下次

调用时，上次的值让然存在,可以说是延长生命周期

extern int count 声明count是一个已定义的外部变量

10、（0815）makefile 的格式

makefile 的一些基本知识：

是一个项目代码管理工具

主要有三个方面：目标：main.o  依赖：main.c  命令: 写时要敲一个tab键

.PHONY clean 是声明伪目标

makefile的特殊符号：

gcc $@ 是目标  $^ 是依赖  $->引用变量  $< 依赖中出现的第一个文件

%,* 都是通配符  但不知道有什么区别

定义变量 CC=gcc

CFLAGS = -Wall -g

在makefile中是树的结构，执行时只执行第一棵树，除特定说明外

vim  Makefile

#this is for chess

第一种：

main:main.c
    gcc main.c -O main -Wall
clean:
    rm -rf main

    rm -rf *.o

    rm -rf ~*

第二种：

#this is for chess

src=main.c

para=-o main -Wall

main:$(src)

    gcc $(src) $(para)     gcc前为一个空格  它在写执行语句时都要敲一个空格

clean:

    rm -rf main

    rm -rf *.o
            
    rm -rf ~*

第二种形式为最好 方便

makefile 的另一种通用格式（万能makefile）


CFLAGS = -Wall -g

CC = gcc

src = $(wildcard *.c)

obj = $(patsubst %.c,%.o,$(src))

main:$(obj)

	$(CC) $^ -o $@

%.o:%.c

	$(CC) $(CFLAGS) $< -c

.PHONY : clean

clean:
	rm -rf *.o

	rm -rf main

11、（0817）有关文件操作的一些基本操作:

FILE 定义文件类型的变量

fopen 打开文 格式：fopen("path" , "mode")

FILE *fp      fclose(fp)

fprintf 输出内容到文件 格式:fprintf(dest fp , "%s\n" , content address)

fscanf 读出文件内容到指定的地方 格式：fscanf(content fp ,"%s",dest address)

但 fscanf 遇到空格就结束

fgets 读出文件内容到指定的地方 格式：

fgets(char *s, int size, FILE *stream)

s 为目标地址  size为输出字符的个数最多为size-1   stream 数据流的来源

fgets(r_str , 5 , fp)

如果输入的字符数大于size 则存size-1个字符 一个‘\0’

如果输入的字符数比size小，则连同回车一起存入

即使是要输入数字，可以通过atoi来实现转换 注意每次输入后，

a[strlen(a)-1] = '\0'  ；里面有一个回车键 num = atoi(a);

fgets 3中结束的条件：

       遇到空格换行  即回车

       达到size的值

       文件内容结束

puts 输出时自动在屏幕上换行 格式：puts("string");

gets 有警告，因为它很有可能越界  实际应用中很少用

fgets 输入时保存回车与换行

gets 输入时不保存回车与换行

getc = fgetc

putc = fputc  返回为整型

#C语言中级

1、(0825)

访问了不该访问的地址：就会出现断错误

在执行一个程序时，实际的内存中会映射出一个虚拟的4G的内存，3G-->4G是系统

运行空间，不能访问和占用，否则会出现断错误   1G-->3G是一个ELF格式的文件

从低地址到高地址分为：text(代码区，机器码)-->rodata(只读数据区,放的是直

接用指针定义的字符串 char *p = "hello",其hello不可以改变；还有用const定

义的变量,如果rodata段没有数据，可以压缩为零)-->data(存放已经初始化的全

局变量，即值不为0的全局变量)-->bss(存放未初始化的全局变量，即使在程序中

给它赋值，它让然在bss段)-->堆空间(可读可写)-->共享库(只可读)-->栈空间(可

读可写)-->命令行参数

变量/函数名--->都是一个符号，是一个地址

功能函数设计注意：<1>名称（知道干什么） <2>传参 <3>返回值

命令行参数，执行命令时写几个就几个 argc 是参数个数 *argv[i]是第i个参数

在输入一个字符串时，可以用*argv[1] *argv[2] ....  和a.out一起输入

有关类型提升：在变量计算时类型提升不会有问题，反过来时会报错

有关exit和return

exit不管在那里，直接退出整个程序

return是结束本函数  在main函数中，它两个作用一样

vim text.c +32(行数) 直接跳到指定的行

2、(0826)有关gdb 是GNU提供的调试器

gdb是针对已经编译通过的程序

在编译时 gcc -Wall -g test.c -o test 加上-g 是使用gdb的前提

run 从头运行该程序，到断点或者程序结束时停止

continue（快捷命令 c）是接着前面的运行，到断点或者程序结束时停止

start 是开始单步执行 遇到错误时就显示错误

next(快捷命令 n) 是执行下一步

enter键是执行上一条命令

print(快捷命令 p) 打印的意思

list(快捷命令l) 打印程序  +10（行号）打印指定的行

break(快捷命令b) 20(行号) 就是在指定行加上断点

info b 查看断点信息

delete(快捷命令d) breakpoint 3( 断点号) 可以删除此断点

运行到一个函数时 step(快捷命令 s) 是进入子函数

一些有关标准输入输出的缓冲区的基本知识：

标准输入输出缓冲区有4096个字节

printf输出的条件(1)遇到'\n'(2)fflush(3)缓冲区满(4)程序结束

fflush()是一个清空缓冲区的函数，清空输入缓冲区时fflush（stdin）,清空输出

缓冲区时fflush（stdout）

链接原理：

即a.c-->a.out

要经过预处理(gcc -E a.i) 编译(gcc -S a.s) 汇编(gcc -c a.o) 链接(gcc a.out)

预处理：展开宏 展开头文件的声明 把注视过滤掉

a.o 中是相对地址  objdump -dxsS 反汇编 机器语言转换成汇编语言 高手可以用来软件

破解

链接：插入启动程序 初始化内存 初始化堆栈 加载共享库 相对地址变化成绝对地址

a.o 和a.out  的区别：地址不同  启动代码不同  执行权限不同

静态库和动态库

静态库，每次运行时，都全部加载在程序中，占内存大

动态库，占内存小

ldd a.out  追踪a.out 依赖的共享库

静态库的有关知识：

静态库的后缀是.o

-L是接路径   -l接的是库名  -I接的是声明文件的路径

gcc a.c b.c -c 生成.o文件

ar rs libstatic.a a.o b.o   生成静态库

动态库的有关知识：

gcc -c -fPIC a.c b.c  生成.o文件  -fPIC 是生成与位置无关的.o文件

gcc -shared -o libstatic.so a.o b.o  生成动态库

共享库的三种路径：

(1) export LD_LIBRARY_PATH=绝对路径   等号两边不能有空格

export LD_LIBRARY_PATH=空   则可以删除这个路径

echo $LD_LIBRARY_PATH  是查看其中有哪些路径

(2) 制作共享库拷贝在共享库的路径下 /usr/lib   /lib  用cp命令即可实现

(3) 修改/etc/ld.so.conf   要以sudo用户登录 修改后还要更新才能生效

sudo ldconfig -v

3、(0827) &*P == *&P ==P

数组和链表的优缺点比较：

数组随机性强  链表增删元素能力强

结构体和数组的比较：

数组不能进行两个之间的赋值  结构体可以进行元素之间的赋值 但在结构体中的数组

可以互相赋值 所以很多时候可以通过结构体给数组赋值


int (*p)[10] 是数组指针

int *p[10] 是指针数组 里面存放的是指针

对于二位数组传参时，可以用 int (*p)[10] 也可以用p[3][4]  但最好是用(*p)[10]

注意在调用时都只写p

对与结构体，为指针时，用-->

为变量时用.

sizeof是在编译时执行  strlen是在运行时执行

const char *p p可以改  *p不可以改

char const *p p可以改  *p不可以改

char *const p p不可以改 *p可以改

char const p  p内容不可以改

char const *const p   p,*p都不可以改

const char  *const p   p,*p都不可以改

可不可以改  主要看const修饰谁

函数指针的定义：

int (*p)(int ,char) 返回值是int型，参数一个整型 一个字符型

int (*p[10])(int ,char) 函数指针数组 ，里面含有十个函数指针 每个返回值都是

int型，参数一个是int型 一个是char型 ，当其元素为无时，返回为NULL



4、(0906)在PC机中，CPU执行程序  内存是运行程序  硬盘是存储程序

系统的任务：1,文件I/O 文件系统 2,进程(一个执行的程序) 线程(是进程的一个单位)

信号(两个程序之间的通讯) 3,内存管理(物理内存 虚拟内存) 4, 网络模块 5,驱动

硬件（实行功能 ，但什么时候实现由应用程序决定）

系统函数和C标准库函数的区别：

系统函数为非标准库函数，只能在UNIX中运行   

C标准库函数 是脱离系统的函数 只要有C编译环境  就可以运行

.exe windows VC编译器

.a.out linux gcc编译器

.c是夸系统平台

printf--->write---->驱动---->显示

硬盘的速度：M/s

现在cpu的速度是G级别的，执行一条指令是1us

硬件存储速度排序：

寄存器是 1us

SRAM一般是作catch用 100us  

SDRAMM(电容充电 用于手机 一个沿采数据) DDRAM(用于PC机 两个沿采数据)

硬盘

msg：表示汇编

启动程序时自动打开3个文件：stdin stdout  stderr

系统函数 ：open write read 无缓冲区  实际上是有个内核缓冲区 时时更新

在man手册中：1是系统命令 2是系统函数 3是C标准库函数 

2 K(大写)  可以直接查看man手册

每打开一个文件，其描述符是：当前没有使用的最小文件描述符

以‘0’ 开始的数是八进制

最多打开1024个描述符，大于1024时会报错,返回-1 

shell解释器本身有一个自带的掩码默认是022，可以用umask查看 也可以umask 数值

对其进行改变

在open函数中，第三个参数和umask进行按位间距与，得到才是open函数中的mode的值

5、（0907） 系统函数 看书

6、（0908） 头文件查找：

cd /usr/src

grep "头文件名字" ./* -R

find ./ -name fcntl.h 文件名

输入重定向<   输出重定向 <

7、（0910） 看书本文件系统

chown root:root 文件名

文件系统：

/dev/sda 是硬盘  /dev/sdb 是U盘

操作步骤：

sudo df   sudo mount /dev/sub /mnt  挂载起来

sudo umount /mnt   卸载

8、（0911）

进程就是一个运行的程序

分时复用CPU实现多进程  

A进程使用CPU 运行态

B进程等待使用CPU 就绪态

C进程睡眠10s 挂起 阻赛

ps -aux 查看进程号   PCB进程块保存当前进程状态

当A进程转B进程时，A数据保存在A进程PCB中

fork()产生两个进程，当子进程不需要写操作时，子父进程共用一段内存 需要写时 在分内存

父进程的ID一定大于子进程的ID

9、（0912）

进程之间的通信方式：

int fd[2]; pipe(fd)创建管道  只使用与父子进程之间通信

mkfifo pipofifo  创建有名管道  使用与任意进程之间的通信

mmap() 函数可以实现进程之间的通信

10、（0913）

signal(信号)

kill -l 打印出所有信号  前32个信号可用

SIGUSR1 SIGUSR2 两个信号由用户定义

man 7 signal man 手册第七部分

kill 可以发送一个信号给指定的进程

kill -11 2379    kill 2379 默认为是发送终止信号

ctrl c 产生信号2  ctrl \ 产生信号3  ctrl z 产生stop 信号

11、（0921）

开源库的使用方法：

(1)解压缩

(2)./configure 检测文件是否有丢失，如果没有生成MAKEFILE

开源库中有./lib 其中有共享库和静态库

(3)make  (4)添加共享库

ifconfig   操作网卡  查看网络信息 mac地址就是网口即硬件地址 独一无二

sudo ifconfig eth0 down 关网卡


sudo ifconfig eth0 up 开网卡

sudo ifconfig eth0 192.168.1.22 命令一个IP

MTU 是最大传输字节数

有关网络号：看路由是否可以ping通

首先ping自己  再ping 别人  再ping 网端  再ping 外网






# tar 

unzip folder.zip -d ~/.file  是解压folder.zip 到主目录下的.file文件

压缩 tar zcvf dir.tar.gz dir

解压 tar zxvf dir.tar.gz

压缩 tar jcvf dir.tar.bz2 dir

解压 tar jxvf dir.tar.bz2

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

刑文鹏老师：
xingwenpeng@akaedu.org
18672230285
#好书推荐
linux一站C编程
深入理解计算机系统
unix环境高级编程（中级）
GNU make
