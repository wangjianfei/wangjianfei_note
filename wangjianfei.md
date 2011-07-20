# vim

##vim 命令的基本模式：  

    Command = operator + number + motion
                d(elete)  1,2
                y(ank)             gg+G

     对 vim的命令的基本操作主要包括以上三个部分

##vim基本命令：
    
   ### 普通模式：
 
     undo 是 u键  撤销上次操作

     redo  是 ctrl+r 撤销超过 返回一步
 
   ### 模行模式：

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
           
     vim 打开多个文件时 

     .vimrc 是vim的配置文件

     vim .vimrc  里面可以写上自己对vim的设置  可以永久生效

     vimtutor 是查看vim的基本命令信息

     写程序时的vim tip：在写vim时，在普通模式时

                    :w 保存文件  必须首先要做

                    :sh 在当前vim上打开一个bash
     
                     ctrl d 或者exit 则可以关闭当前的bash

                其优点是：光标在vim中的位置不会变  较大程序时比较方便


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

      git pull  下载最新的笔记  

      git diff 查看自己现在wangjianfei.md 和.git 里面的wangjianfei.md的区别 

      git reset --hard HEAD 将自己的wangjianfei.md还原成.git 里
            面的wangjianfei.md

      如果已经将垃圾修改生成版本  则可以通过git reset --hard HEAD^ 得到上
             一个版本

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

        开始时首先应该在 .gitconfig 里面添加[core]
                        
                                                     editor = vim

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


##linux basic command  自己掌握

  diff: 
       
       diff -u file.c file1.c   显示两者的不同
    
       diff -u  file.c file1.c  > file.diff  生成差异文件file.diff

       patch file.c < file.diff    生成新文件file.c=flie1.c

       patch -R file.c < file.diff   还原成源文件

  wget  加上网址可以对其进行下载   写上 -r  写上总的网址全部下载

  totem 加上文件名可以对其进行播放
 

##linux command tips

   Clear screen : Ctrl-l  清屏

   Copy and Paste: select -> middle button 复制粘贴

   按方向键即可选择以前用过的命令

   ctrl shift t 可以打开另一个bash

   ctrl pgUp 看上一个bash   ctrl pgDn 看下一个bash
  
   ctrl d  关闭当前bash     在command line write 'exit'

   安装插件的基本格式：sudo apt-get install 插件名 
 

#gcc basic knowledge 编译器基本知识

   gcc -Wall W是指warning 显示警告

             a是指all     显示所有

   linux main的返回值默认是0

   echo $? 是查看函数的返回值

   写程序要考虑硬件则是：低级语言

   写程序不考虑硬件则是：高级语言

   
# tar 

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

## language

   https://github.com/happypeter/job-akae/wiki

## translation

   http://dict.youdao.com/

      有道辞典  通用的IT辞典

   http://learn.akae.cn/media/index.html

