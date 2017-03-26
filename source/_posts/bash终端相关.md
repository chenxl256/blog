---
title: bash终端相关
date: 2017-03-26 16:05:06
tags:
---

1. $echo

   命令echo 表示：输出文本

   ```ruby
   $ echo "hello world"
   ```

   输出结果:hello world

2. $cd

   命令cd表示：进入某文件夹目录，或返回某目录

   1）进入根目录

   ```ruby
   $ cd /
   ```

   2）进入用户目录

   ```ruby
   $ cd ~
   ```

   3）进入某目录(如下：进入bin目录)

   ```ruby
   $ cd bin
   ```

   4）返回到上层目录

   ```ruby
   $ cd ..
   ```

   5）返回上上层目录(中间没用空格)

   ```ruby
   $ cd ../../
   ```

3. pwd

   显示当前所在目录

   ```ruby
   $ pwd
   ```

4. $ls

   命令ls表示：显示本层目录的所有文件和文件夹

   ```ruby
   $ ls
   ```

   当ls后面加上具体的目录时直接输出该文件夹的详细目录信息(比如bin目录如下)

   ```ruby
   $ ls bin
   ```
   显示当前目录下的目录和文件详细列表

   ```ruby
   $ ls -l
   ```

   显示当前目录下的目录和文件详细列表，并方便阅读

   ```ruby
   $ ls -lh
   ```

   显示当前目录下的目录和文件名称，并用颜色区分文件、目录、链接

   ```ruby
   $ ls -G
   ```

   显示当前目录下所有的目录和文件名称，包括隐藏文件

   ```ruby
   $ ls -a
   ```

5. $whereis

   命令whereis表示：查找某程序的路径（比如gcc如下）

   ```ruby
   $ whereis gcc
   ```

   输出结果：/usr/bin/gcc

6. $mkdir

   新建目录（新建文件夹）

   在当前目录下创建名称为hello的文件夹

   ```ruby
   $ mkdir hello
   ```

   新建hello目录，同时在hello目录下创建kitty目录，-p代表递归建立目录

   ```ruby
   $ mkdir -p hello/kitty
   ```

7. $touch

   新建文件，touch的作用是修改文件时间，如果文件不存在，则创建文件

   在当前目录下创建a.txt文件

   ```ruby
   $ touch a.txt
   ```

8. $open

   打开文件或目录

   打开a.txt文件

   ```ruby
   $ open a.txt
   ```

   打开safari.app

   ```ruby
   $ open safari.app
   ```

   打开下载目录

   ```ruby
   $ open ~/DownLoads/
   ```

   打开当前目录

   ```ruby
   $ open .
   ```

9. $mv

   移动文件或目录（剪切）

   将当前目录下的a.txt文件移动到上一级目录

   ```ruby
   $ mv a.txt ..
   ```

   将当前目录下的a.txt文件移动到桌面

   ```ruby
   $ mv a.txt ~/Desktop/
   ```

   将文件a.txt更名为b.txt

   ```ruby
   $ mv a.txt b.txt
   ```

10. $cp

   复制文件或目录

   将文件a.txt复制到桌面

   ```ruby
   $ cp a.txt ~/Desktop/
   ```

   将文件a.txt复制到桌面并且改名为b.txt

   ```ruby
   $ cp a.txt ~/Desktop/b.txt
   ```

   将目录hello复制到上一级目录，-r代表复制到对象为目录

   ```ruby
   $ cp -r hello ..
   ```

11. $rm

    删除文件或者目录

    删除文件a.txt

    ```ruby
    $ rm a.txt
    ```

    删除目录hello

    ```ruby
    $ rm -r hello
    ```

12. $which

    which指令会在环境变量$PATH设置的目录里查找符合条件的文件

    查看指令"bash"的绝对路径

    ````ruby
    $ which bash
    ````

    输出/bin/bash

13. $find

    查找文件，该指令的基本使用格式为find\[path\]\[options\]\[expression\]

    在当前目录下查找“.txt”结尾的文件

    ```ruby
    $ find . -name '*.txt'
    ```

14. 命令记忆功能：

    按上下键，可以查看使用过的所有命令

    这些命令存储在用户目录.bash_history文件中：~/.bash_history

    使用Control+R快捷键，可以搜索输入到历史指令，系统会进行模糊匹配，找到匹配的历史指令

15. 自动补全功能：

    1）按tab键，当在一串指令的第一个词后面，自动补全命令

    2）按tab键，当在一串指令的第二个词后面，自动补全文件名或文件目录

    3）连按两次tab键，（上面两种情况中，若再按一次tab键），则显示所有某些字母开头的命令，或本目录下的所有文件名

16. 快速定位

    Option + 点鼠标击，可以快速定位光标

    Control + A 快速将光标定位到开头

    Control + E 快速将光标定位到结尾

17. 命令别名功能：$alias

    当一条命令太长，可以用alias命令为其他命令设置别名

    例如，要查看本目录下的所有文件，包括隐藏文件，用命令:

    ```ruby
    $ ls -al
    ```

    为了方便记忆，可以为上面的命令取一个别名lsall，操作如下：

    ```ruby
    $ alias lsall＝'ls -al'
    ```

18. $man

    命令man用于查看某命令的详细说明文件，（比如查看ls命令说明如下）

    ```ruby
    $ man ls
    ```

    退出时用输入q

19. $type

    命令type用于判断某命令是不是bash内置命令，或是来自外部（例如cd命令和ls命令如下：）

    ```ruby
    $ type cd
    ```

    输出"cd is a shell builtin"，表示cd是bash内建命令

    ```ruby
    $ type ls
    ```

    输出"ls is hashed (/bin/ls)"，表示ls是外部命令，后面是程序路径

    如果定义了一个命令的别名为lsall，此时用$type命令查看lsall

    ```ruby
    $ type lsall
    ```

    输出"lsall is aliased to `ls -al'"，表示lsall是ls命令的别名

20. 跨行命令，转义命令执行键（转义回车键）

    当输入一行太长的命令时，为了更清楚，可以先输入"\"，然后输入回车键，跳到下一行

    下一行前面会出现">"符号，然后可以继续写没写完的命令

    用两行输入完整的命令，例如：

    ```ruby
    $ cd /Users/xiaoa \回车
    ```

    回车替换为回车符，会在下一样出现">"，继续输入"/test"

    ```ruby
    > /test
    ```

    两行命令等于如下一行：

    ```ruby
    $ cd /Users/xiaoa/test
    ```

21. 在bash中输入$bash命令，将启动一个子bash程序，用$exit命令退出子程序

22. 命令组合，与优先执行

    用反单引号（就是键盘上方数字键1左边的键，不是单引号）包裹命令：｀命令｀

    或$(命令)，来优先执行某个命令，然后把返回的内容作为其他命令的输入，例子如下：

    ```ruby
    $ echo `ls -a`
    ```

    ```ruby
    $ echo $(ls -a)
    ```

    上面的命令语句都有同样的作用：先用$ls命令获得本路径的所有文件名包括.的文件，然后把返回的结果用$echo命令打印出来

    一般用 $(命令) 先执行一段指令的比较多，因为反单引号太容易引起歧义