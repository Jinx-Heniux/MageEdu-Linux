Linux 系统基础使用入门

    第 02 天 【Linux系统基础使用入门(02)】

- 终端：用户与主机交互，必然用到的设备；
    + 物理终端：直接接入本机的显示器和键盘设备；
        * 设备文件路径：`/dev/console`
    + 虚拟终端：附加在物理终端之上的以软件方式虚拟实现的终端，CentOS 6 默认启动 6 个虚拟终端。  
        `切换：Ctrl + Alt + F#: [1,6]`
        * 设备文件路径：`/dev/tty#: [1,6]`
    + 图形终端：附加在物理终端之上的以软件方式虚拟实现的终端，但额外会提供桌面环境；  
        `切换：Ctrl + Alt + F7`
    + 模拟终端：
        * 图形界面下打开的命令行接口，基于 ssh 协议或 telnet 协议等远程打开的界面；
        * 设备文件路径：`/dev/pts/#: [0,oo]`
    + 查看当前使用的终端类型命令：`tty`

- 交互式接口：启动终端后，在终端设备附加一个交互式应用程序
    + GUI：
        * X protocol, window manager, desktop
        * Disktop：
            - GNOME (c,图形开发库：gtk)
            - KDE   (c++, 图形开发库：qt)
            - XFCE  (轻量级桌面)
    + CLI：
        * shell 程序：
            - sh (bourn)
            - csh
            - tcsh
            - ksh (korn)
            - bash (bourn again shell), GPL
            - zsh
        * 显示当前使用的 shell：
             
        ```
            # echo $SHELL      
            /bin/bash    
        ```

        * 显示当前系统使用的所有 shell：  
        
        ```
            # cat /etc/shells   
            /bin/sh  
            /bin/bash  
            /sbin/nologin  
            /bin/dash       
            /bin/false    
        ```

        * 命令提示符：prompt `[root@Testserver ~]#`
            - [root@Testserver ~]: PS1
            - prompt: 
                + 管理员：#
                + 普通用户：$
    + 命令：
        * 输入命令，回车：提请 shell 程序找到键入命令所对应的可执行程序或代码，并由其分析后提交给内核分配资源将其运行起来；
            - 表现为一个或多个进程；
        * 在 shell 中可执行的命令有两类：
            - 内建命令：由 shell 自带的，而且通过某命令形式提供；
            - 外部命令：在当前系统的某文件系统路径下有对应的可执行程序文件。
                + 外部命令可以通过 which, whereis 命令查找。
                + 区别内部或外部的命令：
                    * `# type COMMAND`
        * 运行命令：
            - 命令格式：
                + COMMAND [OPTIONS...] [ARGUMENTS...]
                    * 选项 options：启用或关闭命令的某个或某些功能；
                        - 短选项：-c, 例如：-l, -h
                            + 多个短选项可合并使用，例如 -l -h 可写作 -lh;
                        - 长选项：--word, 例如：--long, --human-readable
                    * 参数 arguments：命令的作用对象，向命令提供数据；
                + **注意**：
                    1. 多个选项，以及多个参数和命令之间都应该使用空白字符分隔。
                    2. 取消命令执行：Ctrl + c 


