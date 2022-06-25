天天都在用的 Tmux，可你知道如何在多用户间共享 Session 吗？
lujun9972 奇妙的Linux世界 2020-02-08 10:38
公众号关注 「运维之美」
设为「星标」，每天带你玩转 Linux ！

Image


Tmux Server 管理着多个 Session，而一个 Session 可以被多个 Tmux Client连接。这些 Tmux Client 通过一个 UNIX Damain Socket 文件来跟 Tmux Server 通讯。


因此，要想让多个用户共享 Tmux Session，只需要指定这些用户调用的 Tmux  Client 连接上同一个 Socket 文件即可。而这可以分成两种情况：


    多个用户使用同一个操作系统帐号

    多个用户使用不同的操作系统帐号


这两者的区别主要在 Socket 文件的权限问题。


多个用户使用同一个操作系统帐号


在多个用户使用同一个操作系统帐号时，不存在用户访问 Socket 文件的权限问题。因此操作起来特别简单，只需要多个用户指定同一个 Tmux Session 名字就行了。


1. 第一个用户新建一个 Tmux Session

$ tmux new-session -s mysession

    

2. 第二个用户连接上这个 Tmux session 即可

$ tmux attach-session -t mysession

多个用户使用不同的操作系统帐号


当多个用户使用不同帐号登录操作系统时，就存在访问 Socket 文件的权限问题了。


那么 Tmux Server 使用的 Socket 文件在哪里呢？


根据 Tmux Manual Page 的说法，Tmux 的 Socket 文件默认为 /tmp/ 或 ${TMUX_TMPDIR}/ 目录下的 default 文件。 


但当使用 -L socket-name 指定 socket-name 时，该 Socket 文件为 /tmp/ 或 ${TMUX_TMPDIR}/ 目录下的 ${socket-name} 文件。甚至，我们可以通过 -S socket-path 的方法来直接指定 Socket 文件的路径。


为了让多个用户在不同帐号间共享 Tmux Session，我们可以这么做：


1. 第一个用户指定一个 Socket 文件来创建 Tmux Session

$ tmux -S /tmp/shared new-session -s shared

 

这时你会看到在  /tmp/ 目录下多了一个 shared 文件。

$ ls -l /tmp/shared
srwxrwx--- 1 lujun9972 lujun9972 0 8月 19 23:25 /tmp/shared

    

你会发现 user 和 group 都有权限对其进行读写。为了让其他账户能够访问Socket 文件，有两种方法：


第一种方法是让这些账户处于同一个用户组 (例如：joint)中，再将 Socket 文件的宿组改为那个用户组( 即：joint 组)

$ usermod -a -G joint user1
$ usermod -a -G joint user2
$ chown :joint /tmp/shared

    

另一种方法当然就是让 Socket 文件让 Other 组也能访问啦。

$ chmod 777 /tmp/shared

    

若其他用户只是查看 Tmux Session 而不做输入的话，也可以不赋予写权限。

$ chmod 775 /tmp/shared

    

解决了权限问题后，其他用户可以通过这个 Socket 文件连接上同一个 Session 了。

$ tmux -S /tmp/shared attach-session -t shared
或者
$ tmux -S /tmp/shared attach-session -t shared -r

    来源：GitHub
    原文：http://t.cn/Ai9xRNon
    题图：来自谷歌图片搜索 
    版权：本文版权归原作者所有
    投稿：欢迎投稿，投稿邮箱: editor@hi-linux.com