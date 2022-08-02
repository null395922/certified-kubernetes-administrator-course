# Two-D-array/Two-D_array.c at main · c-player/Two-D-array · GitHub
[Two-D-array/Two-D_array.c at main · c-player/Two-D-array · GitHub](https://hub.gitfast.tk/c-player/Two-D-array/blob/main/Two-D_array.c) 

 [Permalink](/c-player/Two-D-array/blob/2e4d91d62c91ec31efaacd715a1d59088e2394f4/Two-D_array.c)

main

Switch branches/tags

Branches Tags

[View all branches](/c-player/Two-D-array/branches)

[View all tags](/c-player/Two-D-array/tags)

## [Two-D-array](/c-player/Two-D-array)/**Two-D_array.c**

[Go to file](/c-player/Two-D-array/find/main)

-   [Go to file T](/c-player/Two-D-array/find/main)

-   Go to line L

-   Copy path

-   Copy permalink

This commit does not belong to any branch on this repository, and may belong to a fork outside of the repository.

Cannot retrieve contributors at this time

25 lines (22 sloc) 1.25 KB

[Raw](/c-player/Two-D-array/raw/main/Two-D_array.c) [Blame](/c-player/Two-D-array/blame/main/Two-D_array.c)

 Edit this file

E

[Open in GitHub Desktop](https://desktop.github.com)

-   [Open with Desktop](https://desktop.github.com)
-   [View raw](/c-player/Two-D-array/raw/main/Two-D_array.c)
-   Copy raw contents Copy raw contents Copy raw contents Copy raw contents
-   [View blame](/c-player/Two-D-array/blame/main/Two-D_array.c)

|  | #define \_CRT_SECURE_NO_WARNINGS 1 |

|  | // 关于二维数组地址的理解 |
|  | //sizeof(数组名) 和 & 数组名 中的数组名代表整个数组 |
|  | // 其余数组名代表首元素地址 |

|  | #include &lt;stdio.h> \|

|  | int main() |
|  | { |
|  | int a\[3]\[4] = {0}; |
|  | printf("%d\\n", sizeof(a)); //a 代表整个数组，所以 3 \* 4 \* 4 = 48 |
|  | printf("%d\\n", sizeof(a\[0])); //a\[0]代表第一行的数组名，所以 4 \* 4 = 16 |
|  | printf("%d\\n", sizeof(a\[0] + 1)); //a\[0]是第一行首元素地址，+1 代表第一行第二个元素地址，4 |
|  | printf("%d\\n", sizeof(\*(a\[0] + 1))); // 第二个元素，4 |
|  | printf("%d\\n", sizeof(a + 1)); //a 代表整个数组的首元素地址，即第一行地址，+1 代表第二行地址，4 |
|  | printf("%d\\n", sizeof(\*(a + 1))); // 解引用，找到第二行数组，等价于 sizeof(a\[1])，4 \* 4 = 16 |
|  | printf("%d\\n", sizeof(&a\[0] + 1)); //a\[0]：第一行数组名，数组名取地址，为第一行元素地址，+1 为第二行地址 |
|  | // 注意：a\[0]和 & a\[0]的地址都是相同的，但是代表的含义不同，原来是首元素地址，& 后是整行数组的地址。 4 |
|  | printf("%d\\n", sizeof(\*(&a\[0] + 1)));// 解引用，找到第二行元素，相当于 sizeof(a\[1])，4 \* 4 = 16 |
|  | printf("%d\\n", sizeof(\*a)); //a 是首元素地址，即第一行地址，即 & a\[0]，解引用找到第一行，4 \* 4 = 16 |
|  | printf("%d\\n", sizeof(a\[3])); |
|  | //sizeof 并不会真的去访问第 4 行，sizeof 内部的表达式不参与真实运算，sizeof 只根据类型计算大小， 4 \* 4 = 16 |
|  | return 0; |
|  | } |

-   Copy lines
-   Copy permalink
-   [View git blame](/c-player/Two-D-array/blame/2e4d91d62c91ec31efaacd715a1d59088e2394f4/Two-D_array.c)
-   [Reference in new issue](/c-player/Two-D-array/issues/new)

    Go
