# 大学《C语言程序设计》期末考试题库（完整版含答案） - 知乎
[大学《C 语言程序设计》期末考试题库（完整版含答案） - 知乎](https://zhuanlan.zhihu.com/p/475241853) 

 大学《C 语言程序设计》期末考试题库（完整版含答案） - 知乎

[](//www.zhihu.com)

无障碍写文章

登录 / 注册

![](https://pic2.zhimg.com/v2-ae6fc1515f0533f4d90e065f07f769d1_1440w.jpg?source=172ae18b)

# 大学《C 语言程序设计》期末考试题库（完整版含答案）

[![](https://pic1.zhimg.com/v2-c5b6e9f5e2a0fbd28c20f4c7d8c0a76c_xs.jpg?source=172ae18b)
](//www.zhihu.com/people/ma-ke-tu-bu-44-50)

[彗星撞月亮](//www.zhihu.com/people/ma-ke-tu-bu-44-50)

欢迎进群共同交流 C/C++：981555921 领免费自学资料

26 人赞同了该文章

有些同学上大学学了 C 语言后，是不是感觉不知道自己现在处在什么层次？什么阶段？不知道自己对 C 语言知识的掌握情况？那小编就来考一考你，来做一做下面小编为你特地准备的试题吧~**（如果觉得有用，希望给小编点赞收藏哦！）**

![](https://pic1.zhimg.com/80/v2-72f4f7df4cc1e5efc8e985ad7d9625f8_720w.jpg)

如果想跟小伙伴共同学习交流或者想进一步学习 C/C++ 的同学可以进来跟大家一起，君羊里有小编分享的许多资料题库以及项目实战的源码素材，只要你是真正的想要学习成为更好的自己，以上这些小编都免费送哦！！！

[一起来交流学习 C/C++ 叭~​jq.qq.com/?\_wv=1027&k=jVJiIiG9](https://link.zhihu.com/?target=https%3A//jq.qq.com/%3F_wv%3D1027%26k%3DjVJiIiG9)

**一、单项选择题（本大题共 20 题，每题 2 分，共 40 分）**

1、以下不是 C 语言的特点的是 ( )

A、 C 语言简洁、紧凑

B、能够编制出功能复杂的程序

C、 C 语言可以直接对硬件进行操作

D、 C 语言移植性好

2、以下不正确的 C 语言标识符是 ( )

A、 ABC B、 abc C、 a_bc D、 ab.c

3、一个 C 语言程序是由 ( )

A、一个主程序和若干子程序组成

B、函数组成

C、若干过程组成

D、若干子程序组成

4、一个算法应该具有 “确定性” 等 5 个特性，对另外 4 个特性的描述中错误的

是 ( )

A、有零个或多个输入

B、有零个或多个输出

C、有穷性

D、可行性

5、设变量 a 是整型，f 是实型，i 是双精度型，则表达式 10+‘a’+i\*f 值的数据类型

为 ( )

A、 int B、 float C、 double D、不确定

6、在 C 语言中，char 型数据在内存中的存储形式是 ( )

A、补码 B、反码 C、源码 D、ASCII 码

7、有如下程序，输入数据：12345M678＜cR＞后（<CR>表示回车），x 的值

是 ( ) 。

\#include&lt;stdio.h>

main(){

int x;

float y;

scanf("%3d%f",&x,&y);

}

A、 12345 B、 123

C、 45 D、 345

8、若有以下定义 int a,b; float x，则正确的赋值语句是

( )

A、 a=1,b=2

B、 b++;

C、 a=b=5

D、 b=int(x);

9、以下程序的执行结果是 ( )

\#include&lt;stdio.h>

{

int i=10,j=10;

printf("%d,%d\\n",++i,j--);

}

A、 11,10 B、 9,10

C、 11,9 D、 10,9

10、巳知字母 A 的 ASCII 码是 65，以下程序的执行结果是

( )

\#include&lt;stdio.h>

main()

{

char c1='A',c2='Y';

printf("%d,%d\\n",c1,c2);

A、 A,Y B、 65,65

C、 65,90 D、 65,89

11、下列运算符中优先级最高的是 ( )

A、＜ B、十

C、 % D、 !＝

12、设 x、y 和 z 是 int 型变量，且 x＝3，y＝4，z＝5，则下面表达式中值为 0

是 ( ) 。

A、’x’&&’y’

B、 x＜＝y

C、 x｜｜y+z&&y-z

D、 !((x＜y)＆＆!z ｜｜1)

13、判断 char 型变量 cl 是否为小写字母的正确表达式为 ( )

A、’a’＜＝c1＜＝f’z’ B、 (c1＞＝a)&&(c1＜＝z)

C、(‘a’＞=c1) (‘z’＜＝c1) D、 (c1＞＝’a’)&&(c1＜

＝’z’)

14、字符串 "a" 在内存中占据的字节个数为 ( )

A、 0 B、 1 C、 2 D、 3

15、下面有关 for 循环的正确描述是 ( )

A、 for 循环只能用于循环次数已经确定的情况

B、 for 循环是先执行循环体语句，后判定表达式

C、在 for 循环中，不能用 break 语句跳出循环体

D、 for 循环体语句中，可以包含多条语句，但要用花括号括起来

16、下面程序的运行结果是 ( )

\#include&lt;stdio.h>

main()

{int num=0;

while(num&lt;=2)

{num++;

printf(“%d ,num);

}

}

A、 1

B、 1 2

C、 1 2 3

D、 1 2 3 4

17、以下描述正确的是 ( )

A、由于 do-while 循环中循环体语句只能是一条可执行语句，所以循环体内不

能使用复合语句。

B、 do-while 循环由 do 开始，用 while 结束，在 while（表达式）后面不能写

分号。

C、在 do-while 循环体中，一定要有能使 while 后面表达式的值变成零（“假”）

的操作。

D、 do-while 循环中，根据情况可以省略 while。

18、以下对一维整形数组 a 的正确说明是 ( )

A、 int a(10); B、 int n=10,a\[n];

C、 int n; D、 int a\[10];

scanf(“%d”,&n);

int a\[n];

19、以下对二维数组 a 的正确说明是 ( )

A、 inta\[3]\[]; B、 float a(3,4);

C、 double a\[1]\[4]; D、 float a(3)(4);

20、若二维数组 a 有 m 列，则在 a\[i]\[j]前面的元素个数为 ( )

A、 j\*m+i

B、 i\*m+j

C、 i\*m+j-1

D、 i\*m+j+1

**二、填空题（本大题共 10 空，每空 2 分，共 20 分）**

1、结构化设计中的三种基本结构是\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

2、在 C 语言中的实型变量分为两种类型，它们是\_\_\_\_\_\_\_\_ 和

\_\_\_\_\_\_\_\_\_

3、当 a=5,b=4,c=2 时，表达式 a>b!= c 的值是\_\_\_\_\_\_\_

4、下列程序运行后的输出结果是\_\_\_\_\_\_\_\_\_\_\_\_\_

\#include&lt;stdio.h>

main()

{

int i,j;

for(i=4;i>=1;i--)

{printf("\* ");

for(j=1;j&lt;=4-i;j++)

printf("\* ");

printf("\\n");

}

5、若有定义：int a\[3]\[4]={{1,2},{0},{4,6,8,10}}；则初始化后，a\[1]\[2]得到的初值是

\_\_\_\_\_\_\_\_\_\_\_ a\[2]\[1]得到的初值是\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

6、在 C 语言中，二维数组元素的内存中的存放顺序是\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**三、程序分析题（本大题共 2 题，每题 4 分，共 8 分，描述程序功能并写出程序执行结果）**

1、#include&lt;stdio.h>

main( )

{int a,s,n,count;

a=2;s=0;n=1;count=1;

while(count&lt;=7) {n=n\*a; s=s+n; ++count;}

printf(“s=%d”,s);

}

2、#include&lt;stdio.h>

main()

{int a=\[3]\[3]={1,3,5,7,9,11,13,15,17},sum=0,i,j;

for (i=0;i&lt;3;i++)

for(j=0;j&lt;3;j++)

if (i==j) sum=sum+a\[i]\[j];

printf(“sum=%d\\n”,sum);

}

**四、编程题（本大题共 4 题，每题 8 分，共 32 分）**

1、编写摄氏温度、华氏温度转换程序。要求：从键盘输入一个摄氏温度，屏幕就显示对应

的华氏温度，输出取两位小数。转换公式：F=（C+32）×9/5 。

2、试编程判断输入的正整数是否既是 5 又是 7 的正倍数。若是，则输出 yes；否则输出 no。

3、判断数 m 是否为素数（只能被 1 和它本身整除的整数）?

4、对 15 个数进行排序，按从小到大的顺序输出。

## **大学《C 语言程序设计》期末考试题库（完整版含答案）**

一、单项选择题（本大题共 20 题，每题 2 分，共 40 分）

1、 B 2、 D 3、 B 4、 B 5、 C

6、 D 7、 B 8、 B 9、 A 10、D

11、C 12、D 13、D 14、C 15、D

16、C 17、C 18、D 19、C 20、B

二、填空题（本大题共 10 空，每空 2 分，共 20 分）

1、顺序结构分支结构循环结构

2、单精度型 (或：float 型) 双精度型 (或；double 型]

3、 1

4、 \*

\* \*

\* \* \*

\* \* \* \*

5、 0 6

6、按行主顺序存放

三、程序分析题（本大题共 2 题，每题 4 分，共 8 分）

能正确表达出题目的含义、要求，即可得分, 部分正确可按比例得分, 否则不得分。

1、功能：求 S=0+2+4+8+16+32+64+128 和。

输出结果：s=254

2、功能：出矩形阵 a 的主对角线上的元素之和。

输出结果：27

四、编程题（本大题共 4 题，每题 8 分，共 32 分）

能正确表达出题目的含义、要求，且格式正确，即可得满分，不要求形式完全相同。部分正

确可按比例得分, 否则不得分。

1、 #include&lt;stdio.h>

main()

{ float c,f;

printf("input c:"); …………………………………………….2 分

scanf("%f",&c); …………………………………………….2 分

f= (c+32.0)\*9.0/5.0; …………………………………………….2 分

printf("F=%.2f \\n ",f); …………………………………………….2 分

}

2、#include&lt;stdio.h>

main()

{int x;

scanf("%d",&x); …………………………………………….2 分

if(x%5==0&&x%7==0) …………………………………………….2 分

printf("yes");…………………………………………….2 分

else

printf("no");…………………………………………….2 分

}

3、 # include &lt;stdio.h>

\# include &lt;math.h>

main()

{int m,i,k;

scanf("%d\\n",&m);

k=sqrt(m); …………………………………………….2 分

for(i=2;i&lt;=k;i++)…………………………………………….2 分

{if(m%i==0)

break; …………………………………………….2 分

}

if(i>k)

printf("m is a prime number!\\n");…………………………………………….2 分

}

4、 # include &lt;stdio.h>

main()

{int i,j,a\[15],t;

printf("input 15 numbers:\\n");

for(i=0;i&lt;15;i++)

scanf("%d",&a\[i]); …………………………………………….2 分

for(j=0;j&lt;15;j++)…………………………………………….2 分

for(i=0;i&lt;15-j;i++)…………………………………………….2 分

if(a\[i]>a\[i+1])

{t=a\[i];a\[i]=a\[i+1];a\[i+1]=t;} …………………………………………….2 分

for(i=0;i&lt;15;i++)

printf("%6d",a\[i]);

}

发布于 2022-03-03 14:54

\[

C（编程语言）

](//www.zhihu.com/topic/19561633)

\[

试题库

](//www.zhihu.com/topic/19792021)

\[

大学生期末考

](//www.zhihu.com/topic/23586184)

​赞同 26​​6 条评论

​分享

​喜欢​收藏​申请转载

​

赞同 26

​

分享

## 6 条评论

​切换为时间排序

写下你的评论...

发布

精选评论（1）

-   [![](https://pica.zhimg.com/v2-c5b6e9f5e2a0fbd28c20f4c7d8c0a76c_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/ma-ke-tu-bu-44-50)

    [彗星撞月亮](//www.zhihu.com/people/ma-ke-tu-bu-44-50) (作者) IP 属地未知 · 03-03

    对于刚接触 C/C++ 的伙伴来说，会很困惑迷茫，觉得值不值投入精力去学习，在学的过程中，遇到问题很难得到解决。不知道需要学到什么程度，不知道自己接下来要怎么学，小编也是过来人，为此建了一个裙，大家可以一起学习交流，还有一些资料帮助大家更好的学习

    ​2​回复​踩​ 举报

评论（6）

-   [![](https://pic4.zhimg.com/v2-ce0da260a3c7bfe89e4a1e2d3211ba25_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/wei-xin-yong-hu-26-25-34)

    [扣扣耀耀](//www.zhihu.com/people/wei-xin-yong-hu-26-25-34)​IP 属地湖南 · 06-23

    bdbbc  
    dbbad  
    cddcd  
    cdccb

    ​赞​回复​踩​ 举报


-   [![](https://pica.zhimg.com/v2-368e5db9d93224c1e3887991171c8ded_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/huan-le-59-14)

    [欢乐](//www.zhihu.com/people/huan-le-59-14)IP 属地贵州 · 06-01

    C 不可以直接对硬件直接操作好吧

    ​赞​回复​踩​ 举报


-   [![](https://pic1.zhimg.com/v2-abed1a8c04700ba7d72b45195223e0ff_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/yjr-43-93)

    [YJR](//www.zhihu.com/people/yjr-43-93)IP 属地广东 · 05-25

    第 16 题为什么啊

    ​赞​回复​踩​ 举报


-   [![](https://pic2.zhimg.com/v2-86a6d2e6a7ce51e5f6529ef85b53e5c5_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/zhao-xiao-jie-80-73)

    [趙潇婕](//www.zhihu.com/people/zhao-xiao-jie-80-73)IP 属地未知 · 03-30

    专升本考 C 程序设计，有适合的题库吗？

    ​赞​回复​踩​ 举报


-   [![](https://pica.zhimg.com/v2-c5b6e9f5e2a0fbd28c20f4c7d8c0a76c_s.jpg?source=06d4cd63)
    ](//www.zhihu.com/people/ma-ke-tu-bu-44-50)

    [彗星撞月亮](//www.zhihu.com/people/ma-ke-tu-bu-44-50) (作者) IP 属地未知 · 03-03

    981555921

    ​赞​回复​踩​ 举报

### 推荐阅读

\[

![](https://pic4.zhimg.com/v2-c8be3fcc7bf4a96c38d4ee3417bce36d_250x0.jpg?source=172ae18b)

# C 语言学习易错知识点总结 | 来看看我的刷题经验！

summer

]([https://zhuanlan.zhihu.com/p/481707825](https://zhuanlan.zhihu.com/p/481707825))\[

# 【大学期末突击宝典之 C 语言】

C 语言最简单最有效的史诗级教程来了！只需半天看完必过！！！大学生到了期末都非常头痛一门课程——《C 语言》。据了解这门课程的挂科率甚至达到了 30% 以上。 此篇教程适用于对 C 语言有学习需…

暮雨学长发表于大学干货铺

]([https://zhuanlan.zhihu.com/p/142734040](https://zhuanlan.zhihu.com/p/142734040))\[

# C 语言期末复习

临近期末，小伙伴们都开始进行期末复习了吧！实话实说，有一说一，第一次在知乎上发文章，我不是 C 语言的大佬，也是上大学后初识 C 语言。所以大佬们自动退出哈，本文仅适用于正在准备期末复习…

生活咖啡厅

]([https://zhuanlan.zhihu.com/p/98100359](https://zhuanlan.zhihu.com/p/98100359))\[

![](https://pic2.zhimg.com/v2-ef262b17419c0b05eff06b868cec3cc2_250x0.jpg?source=172ae18b)

# 【C 语言解惑课堂】解惑内容合集 (2019.8.18 更新)

C 语言答疑课堂

]([https://zhuanlan.zhihu.com/p/78715883](https://zhuanlan.zhihu.com/p/78715883))

_想来知乎工作？请发送邮件到 jobs@zhihu.com_

![](https://static.zhihu.com/heifetz/assets/liukanshan-peek.89f777ce.png)
登录即可查看 超 5 亿 专业优质内容

超 5 千万创作者的优质提问、专业回答、深度文章和精彩视频尽在知乎。

立即登录 / 注册
