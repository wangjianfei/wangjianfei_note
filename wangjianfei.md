# vim

    Command = operator + number + motion
                d(elete)  1,2
                y(ank)             gg+G
     对 vim的命令的基本操作主要包括以上三个部分
     
     在vim中要粘贴  必须进入插入模式

# markdown

    http://happypeter.github.com/LGCB/book/toy_markdown.html
    是peter老师的笔记

### html study

http://www.w3schools.com/ 
       学习 html语言  

# git
## install

    sudo apt-get install git-core 安装 git  管理软件的软件
    sudo apt-get install tig     安装  tig   查看软件修改的地方

    git pull  更新笔记  
## git basics   git 的基本操作步骤

1. first create a dir

        mkdir ggg

2. now you MUST cd to this dir

        cd ggg

3. initializing this git dir

        git init

    now you can see a `.git` in this dir

        ls -a

4. now create a file

        vim hello.c

5. let git knows about this file

        git add hello.c

6. create the first version

        git commit -a -m "my first version"
    -a :是all的意思  即跟踪所有修改地方
    -m :是message的意思    后面跟上修改留言

#账户申请
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
      

##When you're done:

  Continue



# ref

http://progit.org/

        通过最下面的 chinese 可以转换成中文

video: search "linus git" at youku.com

# linux basics

Linux is OS(operating system)

OS as linus see it:

OS is nothing but the kernel.

Linux is nothing but the kernel.

ubuntu is Linux + 1000 app.

OS as MS see it:

OS is kernel + desktop env.
# tips

   Clear screen : Ctrl-l  

   Copy and Paste: select -> middle button

## language

https://github.com/happypeter/job-akae/wiki

## translation

http://dict.youdao.com/
    
      有道辞典  通用的IT辞典

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

### path

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
