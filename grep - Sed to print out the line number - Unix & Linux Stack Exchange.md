# grep - Sed to print out the line number - Unix & Linux Stack Exchange
[grep - Sed to print out the line number - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/526064/sed-to-print-out-the-line-number) 

 Here is my sample file

```
user@linux:~$ cat file.txt 
Line 1
Line 2
Line 3
Line 4
Line 5
user@linux:~$ 

```

I can print line 2-4 with `grep -A2 'e 2' file.txt`

```
user@linux:~$ grep -A2 'e 2' file.txt 
Line 2
Line 3
Line 4
user@linux:~$ 

```

I can also print out the line number as well with `grep -n`

```
user@linux:~$ grep -nA2 'e 2' file.txt 
2:Line 2
3-Line 3
4-Line 4
user@linux:~$ 

```

Also, the same thing can be accomplished with `sed -n 2,4p file.txt`

```
user@linux:~$ sed -n 2,4p file.txt 
Line 2
Line 3
Line 4
user@linux:~$ 

```

But I'm not sure how to print out the line number with `sed`

Would it be possible to print out the line number with `sed`?

asked Jun 20, 2019 at 14:59

5

**AWK:**

```
awk 'NR==2,NR==4{print NR" "$0}' file.txt

```

Double **sed:**

```
sed '2,4!d;=' file.txt | sed 'N;s/\n/ /'

```

[glen jackmann](https://unix.stackexchange.com/users/4667/glenn-jackman)'s **sed** and **paste:**

```
sed '2,4!d;=' file.txt | paste -d: - -

```

[bart](https://unix.stackexchange.com/users/152035/bart)'s **Perl** version:

```
perl -ne 'print "$. $_" if 2..4' file.txt

```

**cat** and **sed:**

```
cat -n file.txt | sed -n '2,4p'

```

* * *

Also see this [answer](https://unix.stackexchange.com/a/225446/265461) to a similar question.

A bit of **explanation:**

-   `sed -n '2,4p'` and `sed '2,4!d;='` do the same thing: the first only prints lines between the second and the fourth (inclusive), the latter "deletes" every line except those.
-   `sed =` prints the line number _followed by a newline_. See the [manual](https://www.gnu.org/software/sed/manual/sed.html#index-_003d-_0028print-line-number_0029-command).
-   `cat -n` in the last example can be replaced by `nl` or `grep -n ''`.

answered Jun 20, 2019 at 15:11

\[

![](https://i.stack.imgur.com/sWGmO.png?s=64&g=1)

]([https://unix.stackexchange.com/users/265461/simlev](https://unix.stackexchange.com/users/265461/simlev))

[simlev](https://unix.stackexchange.com/users/265461/simlev)simlev

1,2652 gold badges9 silver badges19 bronze badges

2

I have done by below mentioned 2 methods

Method1

```
awk '/2/{x=NR+2}(NR<=x){print NR"-"$0 }' filename

```

command

```
2-Line 2
3-Line 3
4-Line 4

```

Method2

```
sed -n '{;=;p}' filename| sed "N;s/\n/ /g"| sed -n '/2/,+2p'

```

output

```
2 Line 2
3 Line 3
4 Line 4

```

answered Jun 20, 2019 at 15:37

\[

![](https://www.gravatar.com/avatar/5c651f1a15c64805ef2ab383c15e8085?s=64&d=identicon&r=PG)

]([https://unix.stackexchange.com/users/259343/praveen-kumar-bs](https://unix.stackexchange.com/users/259343/praveen-kumar-bs))

[Praveen Kumar BS](https://unix.stackexchange.com/users/259343/praveen-kumar-bs)Praveen Kumar BS

4,7612 gold badges8 silver badges13 bronze badges
