# 用sed和awk实现将文本中的上下多行合并为一行_ethnicitybeta的博客-CSDN博客_awk多行合并一行
[用 sed 和 awk 实现将文本中的上下多行合并为一行\_ethnicitybeta 的博客 - CSDN 博客\_awk 多行合并一行](https://blog.csdn.net/ethnicitybeta/article/details/122600443?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EOPENSEARCH%7Edefault-2-122600443-blog-93158334.pc_relevant_multi_platform_whitelistv4eslandingrelevant&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EOPENSEARCH%7Edefault-2-122600443-blog-93158334.pc_relevant_multi_platform_whitelistv4eslandingrelevant&utm_relevant_index=3) 

 假设文本中的内容为：

要求将文本内容处理为：

（中间以制表符分隔）

方法一：

```null
sed -n '{N;s/\n/\t/p}' test.txt
```

方法二：

```null
awk '{tmp=$0;getline;print tmp"\t"$0}' test.txt
```

[文本操作 (awk,sed) 三行合并为一行 ](https://www.cnblogs.com/yunzhongzhuhuo/articles/4566801.html "文本操作 (awk,sed) 三行合并为一行 ")

linux 下的文本操作 

### sed 方法：

```null
　　sed 'N;N;s/\n/ /g' test.txt
```

说明：N 追加下一个输入行到模式空间，用了两次把当前行的后两行都追加到了模式空间，即多行模式空间。让后用 s 将\\n 换行符替换成空格。最后的 g 是全局替换即替换所有的\\n, 若不加 g 表示只替换第一个。

```null
　　awk 'ORS=NR%3?" ":"\n"{print}' test.txt[root@localhost abc]# awk 'ORS=NR%3?" ":"\n"{print}' test.txt
```

或者将其输入至另一个文件

```null
awk 'ORS=NR%3?" ":"\n"{print $0 >> "abc" }' test.txt
```

基本语法：

```null
sed "s/要匹配的字符串/要替换成的字符串/g" test.gson
```

语法解释：sed 是按行处理文本数据的，每次处理一行数据后，都会在行尾自动添加 trailing newline，其实就是行的分隔符即换行符。连续两行执行一次 sed 命令，这样就可以把前一行的\\n 替换完成。（Ps：执行一次命令其实就是数据两两去除了中间的\\n 而已）

（多行）替换 / 删除所有换行符（变一行）：

```null
sed  -i  ":a;N;s/\\n//g;ta"  test.gson
```

语法解释：前边加上（:a;N;） 后边加上（ ;ta）将解决上面所说的一次命令只能替换文本二分之一内容的问题

（一行）拆分成独立行（变多行）：

```null
sed -i "s/拆分符/拆分符\\n/g" test.gson
```
