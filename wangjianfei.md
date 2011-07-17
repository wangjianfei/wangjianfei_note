# vim

##vim 命令的基本模式：  

    Command = operator + number + motion
                d(elete)  1,2
                y(ank)             gg+G

     对 vim的命令的基本操作主要包括以上三个部分

##vim基本命令：

##vim的tip:

     在vim中要粘贴  必须进入插入模式

#两种网页编写语言：

##markdown

    http://happypeter.github.com/LGCB/book/toy_markdown.html  是peter老师的笔记

    __word__  可以将 word 变成粗体

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

    git pull  下载最新的笔记  

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

        tig查看版本
      
       ref:    http://progit.org/

       通过最下面的 chinese 可以转换成中文

       video: search "linus git" at youku.com 纯英语

#github账户申请

##github的申请：

    打开主页，点击“”，
    
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

  git push -u origin __ master__  是主仓库的意思
      

##Existing Git Repo?

  cd existing_git_repo

  git remote add origin git@github.com:wangjianfei/wangjianfei_note.git

  git push -u origin master
      

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

##linux basic command  自己掌握

  diff: 
       
       diff -u file.c file1.c   显示两者的不同
    
       diff -u  file.c file1.c  > file.diff  生成差异文件file.diff

       patch file.c < file.diff    生成新文件file.c=flie1.c

       patch -R file.c < file.diff   还原成源文件

##linux command tips

   Clear screen : Ctrl-l  

   Copy and Paste: select -> middle button

   按方向键即可选择以前用过的命令


# shell ( shell is a commandline interpreter)

bash is a kind of shell. 

## filesystem tree

    ls

    cd 
    # ~ means your home dir
    cd .. # go to the parent of current dir

    pwd

    man pwd # q to quit

    mkdir dir

## path

    绝对路径: start with /
    相对路径: start with .

## shell prompt

    peter@cow:~/tg-note$
    user@machinename:currentWorkingDirectory(folder)$

# software installation

    sudo apt-get install tree


# tar 

http://www.happypeter.org/posts/10

# ref

http://happypeter.github.com/LGCB/

http://billie66.github.com/TLCL/book/


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

