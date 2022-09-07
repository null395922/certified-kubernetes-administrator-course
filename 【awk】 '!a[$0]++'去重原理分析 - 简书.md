# 【awk】 '!a[$0]++'去重原理分析 - 简书
[【awk】 '!a\[$0\]++'去重原理分析 - 简书](https://www.jianshu.com/p/84074efd7199) 

 [![](https://upload.jianshu.io/users/upload_avatars/9589088/76687522-83e4-421a-9db4-13e98203bbf8?imageMogr2/auto-orient/strip|imageView2/1/w/96/h/96/format/webp)
](https://www.jianshu.com/u/d0675dcb6154)

0.372019.01.22 23:27:42 字数 762 阅读 2,529

[原文](https://links.jianshu.com/go?to=https%3A%2F%2Fsapser.github.io%2Fshell%2F2014%2F08%2F07%2Fawk-remove-duplicate-analyze)

很多人都知道 awk '!a\[$0]++' file 可以去除文本中重复的行，但是对其到底是如何去重的却不是很清楚，所以这里就单独来分析一下这个命令。

首先我们要知道这条命令是隐含了一个 print $0 的，完整命令如下：

    $ cat c
    1
    2
    2
    3
    1
    3
    3

    $ awk '!a[$0]++{print $0}' c
    1
    2
    3 

awk 判定以下三种情况为 “假”，其他情况都为 “真”：

数字`0`  
空字符串`""`  
未定义的变量，对于未定义的变量 var，如果要进行字符串操作，会被转成空字符串`""`，如果要进行数学运算，会被转成数字`0`，也可以使用`var""`来强制转为空字符串`""`，`var+0`来强制转为数字`0`  
所以上面这条 awk 语句的原理就是判断! a\[$0]++ 的值，如果值为真就打印当前行，值为假自然就不会打印当前行了。

开始分析! a\[$0]++ 吧，不过还得先看一下 awk 中操作符的优先级（由高到低排列）：

    $                #字段引用($1,$2)
    ++ --
    ^ **             #求幂
    + - !            #正、负、逻辑非       
    * / %
    + -              #加法减法
    (blank)          #连接符
    < <= == != > >=
    ~ !~ 
    &&
    ||
    ?:   
    = += -= *= /= %= ^= **=    
    这里看到++操作符优先级是高于!操作符的。 

    现在正式开始分析!a[$0]++，先使用{print ">"a[$0]+0}来输出每次进行!a[$0]++计算后a[$0]的值：
    $ echo -e "5\n5\n5"|awk '{print ">"a[$0]+0}!a[$0]++{print $0}'
    >0
    5
    >1
    >2 

    为了简化输出，这里只对相同的三行进行去重，可以看到处理第一行之前a[$0]还是未定义的，
    所以输出为空（这里通过a[$0]+0强制转换成了0），当第一行处理完成之后a[$0]的值变成了1，
    第二行处理完成之后a[$0]的值变成了2，以此类推。 

这里我们可以将 a\[$0]数组取值替换为一个简单的变量，方便理解：

    $ awk 'BEGIN{a=0;print !a++,a}'
    1 1
    $ awk 'BEGIN{a=1;print !a++,a}'
    0 2
    $ awk 'BEGIN{a=2;print !a++,a}'
    0 3 

我们知道 a++ 操作符是在变量 a 使用完之后再对变量进行自增，所以这里虽然 ++ 比! 优先级高，先跟变量 a 结合，但是不会立即自增变量 a 的值，而是在! a 之后在自增变量 a 的值。通过例子来理解：

    变量a的值为0，`!a`取反后返回1，然后`a++`将变量a的值自增1，此时`!a++`返回的值就是`!a`计算出来的1，同时变量a的值也变为了1
    变量a的值为1，`!a`取反后返回0，然后`a++`将变量a的值自增1，此时`!a++`返回的值就是`!a`计算出来的0，同时变量a的值变为2
    变量a的值为2，`!a`取反后返回0，然后`a++`将变量a的值自增1，此时`!a++`返回的值就是`!a`计算出来的0，同时变量a的值变为3 

现在是不是一目了然了，再代入回之前的例子中：

    $ echo -e "5\n5\n5"|awk '{print ">"a[$0]+0}!a[$0]++{print $0}'
    >0
    >1
    >2 

分析如下：

> 开始处理第一行之前，`a[$0]`是未定义的，所以值为空 (相当于上面的`a=0`)，`!a[$0]`取反返回 1，然后`a[$0]++`将`a[$0]`的值自增 1，此时`![$0]++`返回的值就是`!a[$0]`计算出来的 1，数字 1 在 awk 中为真，所以会执行后面的`{print $0}`输出第一行，同时`a[$0]`的值也变为了 1  
> 开始处理第二行之前，`a[$0]`值为 1(相当于上面的`a=1`)，`!a[$0]`取反返回 0，然后`a[$0]++`将`a[$0]`的值自增 1，此时`![$0]++`返回的值就是`!a[$0]`计算出来的 0，数字 0 在 awk 中为假，所以不会执行后面的`{print $0}`来输出第二行，同时`a[$0]`的值变为 2  
> 开始处理第三行之前，`a[$0]`值为 2(相当于上面的`a=2`)，`!a[$0]`取反返回 0，然后`a[$0]++`将`a[$0]`的值自增 1，此时`![$0]++`返回的值就是`!a[$0]`计算出来的 0，数字 0 在 awk 中为假，所以不会执行后面的`{print $0}`来输出第三行，同时`a[$0]`的值变为 3  
> 分析完成，不过这只是我个人的理解，有不对的地方请回复指出，一起学习！

更多精彩内容，就在简书 APP

"小礼物走一走，来简书关注我"

还没有人赞赏，支持一下

[![](https://upload.jianshu.io/users/upload_avatars/9589088/76687522-83e4-421a-9db4-13e98203bbf8?imageMogr2/auto-orient/strip|imageView2/1/w/100/h/100/format/webp)
](https://www.jianshu.com/u/d0675dcb6154)

[caokai001](https://www.jianshu.com/u/d0675dcb6154 "caokai001")[![](https://upload.jianshu.io/user_badge/19c2bea4-c7f7-467f-a032-4fed9acbc55d)
](https://www.jianshu.com/mobile/creator)HZAU 植科院农学本科毕业生<br>HZAU 信息学院生信专业硕士毕业生<br>目前就职于国内某...

总资产 171 共写了 19.6W 字获得 1,155 个赞共 1,567 个粉丝

### 被以下专题收入，发现更多相似内容

### 推荐阅读[更多精彩内容](https://www.jianshu.com/)

-   转载 原文的排版和内容都更加友好, 并且详细, 我只是在这里贴出了一部分留作自己以后参考和学习, 如希望更详细了解 AWK...

    [![](https://cdn2.jianshu.io/assets/default_avatar/5-33d2da32c552b8be9a0548c7a4576607.jpg)
    XKirk](https://www.jianshu.com/u/6edda70f80ee)阅读 2,915 评论 2 赞 25
-   Linux 指令中文说明传送入口 整理自 Linux 指令中文说明 文本和数据进行处理的编程语言 awk 是一种编程语言，...

    [![](https://upload.jianshu.io/users/upload_avatars/11628999/58bb51d8-c535-48cb-92f5-1adb617eb01f.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/48/h/48/format/webp)
    释闲人](https://www.jianshu.com/u/140374c05fa2)阅读 1,385 评论 1 赞 6


-   栈 1. 栈（stack）又名堆栈，它是一种运算受限的线性表。其限制是仅允许在表的一端进行插入和删除运算。这一端被...
-   官网 中文版本 好的网站 Content-type: text/htmlBASH Section: User ...

    [![](https://cdn2.jianshu.io/assets/default_avatar/4-3397163ecdb3855a0a4139c34a695885.jpg)
    不排版](https://www.jianshu.com/u/97702e424c5d)阅读 3,796 评论 0 赞 5
-   awk: grep,sed,awk grep：文本过滤 sed：文本编辑 awk：文本格式化工具； 1 什么是 aw...

    [![](https://cdn2.jianshu.io/assets/default_avatar/12-aeeea4bedf10f2a12c0d50d626951489.jpg)
    木林森](https://www.jianshu.com/u/483abec9f381)阅读 1,416 评论 0 赞 16
-   原文：评判式回应是用某种方式去评价别人的行为和想法。这样的评判可能是讨人喜欢的，也有可能是不讨人喜欢的。 理解：说...

    [![](https://cdn2.jianshu.io/assets/default_avatar/3-9a2bcc21a5d89e21dafc73b39dc5f582.jpg)
    王朋彦](https://www.jianshu.com/u/b866eeaa5b85)阅读 189 评论 4 赞 0


-   桃子觉得最近黑得不行，不是皮肤黑，是运气黑到不行。 究其原因，就是因为那个陈建南。陈建南是桃子所在销售部的部门总监...

    [![](https://cdn2.jianshu.io/assets/default_avatar/1-04bbeead395d74921af6a4e8214b4f61.jpg)
    阡陌末](https://www.jianshu.com/u/c2d7324f9c3d)阅读 743 评论 18 赞 13

    [![](https://upload-images.jianshu.io/upload_images/3240574-cf10f7f1db51c3d0.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240/format/webp)
    ](https://www.jianshu.com/p/2bff2022fcd5)
-   一直从事企业产品的互联网推广工作，下面我给大家分享一下这个话题。 目前互联网推广方式中转化率最高的就是 SEO 了，那...
