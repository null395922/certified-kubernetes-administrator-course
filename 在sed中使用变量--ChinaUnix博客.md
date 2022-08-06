# 在sed中使用变量--ChinaUnix博客
来源：[在 sed 中使用变量 --ChinaUnix 博客](http://blog.chinaunix.net/uid-26495963-id-3205420.html)

## 摘录内容

[在 sed 中使用变量](/uid-26495963-id-3205420.html)

分类： LINUX

2012-05-12 13:18:06

举例说明：变量 a 和 b，使用 sed 的替换命令将 $a 替换为 $b  
1.eval sed 's/$a/$b/' filename  
2.sed "s/$a/$b/" filename  
3.sed 's/'$a'/'$b'/' filename  
4.sed s/$a/$b/ filename  

如果对某个文件进行更改加 -i 选项

## 想法
