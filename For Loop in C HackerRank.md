# For Loop in C | HackerRank
[For Loop in C | HackerRank](https://www.hackerrank.com/challenges/for-loop-in-c/problem) 

      For Loop in C | HackerRank                                                                                              

-   [![](https://hrcdn.net/community-frontend/assets/brand/logo-new-white-green-a5cb16e0ae.svg)
    ](/dashboard)

-   \[Prepare

    NEW

    ](/dashboard)

-   [Certify](/skills-verification)

-   [Compete](/contests)

-

-   a444395922

1.  [Prepare](/dashboard)
2.  [C](/domains/c)
3.  [Conditionals and Loops](/domains/c/c-conditionals-and-loops)
4.  For Loop in C

# For Loop in C

=================================

35 more points to get your next star!

Rank: 424157|Points: 15/50[](/scoring)

C language

\[

Problem

](/challenges/for-loop-in-c/problem)\[

Submissions

](/challenges/for-loop-in-c/submissions)\[

Leaderboard

](/challenges/for-loop-in-c/leaderboard)\[

Discussions

](/challenges/for-loop-in-c/forum)\[

Editorial

](/challenges/for-loop-in-c/editorial)

**Objective**

In this challenge, you will learn the usage of the _for_ loop, which is a programming language statement which allows code to be executed until a terminal condition is met. They can even repeat forever if the terminal condition is never met.

The syntax for the `for` loop is:

```
for ( <expression_1> ; <expression_2> ; <expression_3> )
    <statement>

```

-   _expression_1_ is used for intializing variables which are generally used for controlling the terminating flag for the loop.
-   _expression_2_ is used to check for the terminating condition. If this evaluates to false, then the loop is terminated.
-   _expression_3_ is generally used to update the flags/variables.

The following loop initializes to 0, tests that is less than 10, and increments at every iteration. It will execute 10 times.

```
for(int i = 0; i < 10; i++) {
    ...
}

```

**Task**

For each integer in the interval (given as input) :

-   If , then print the English representation of it in lowercase. That is "one" for , "two" for , and so on.
-   Else if and it is an even number, then print "even".
-   Else if and it is an odd number, then print "odd".

**Input Format**

The first line contains an integer, .  
The seond line contains an integer, .

**Constraints**

**Output Format**

Print the appropriate English representation,`even`, or `odd`, based on the conditions described in the 'task' section.

**Note:**

**Sample Input**

```
8
11

```

**Sample Output**

```
eight
nine
even
odd

```

Change Theme

Language: C

More

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

\#include&lt;stdio.h>

\#include&lt;string.h>

\#include&lt;math.h>

\#include&lt;stdlib.h>

int main() 

{

int a, b;

    scanf("%d\\n%d", &a, &b);

char labels\[11]\[6] = {"one", "two", "three", "four", "five", "six", "seven", "eight",

"nine", "even", "odd"};

int labels_index;

for (int i=a; i&lt;=b; i++) {

        labels_index = i &lt;= 9 ? i - 1 : 9 + i % 2;

        printf("%s\\n", labels\[labels_index]);

    }

return0;

}

Line: 20 Col: 1

Submit Code

Run Code

Upload Code as File

Test against custom input

Author

[abhiranjan](/profile/abhiranjan)

Difficulty

Easy

Max Score

10

Submitted By

[260625](/challenges/for-loop-in-c/leaderboard)

## Need Help?

* * *

[View discussions](/challenges/for-loop-in-c/forum)

[View editorial](/challenges/for-loop-in-c/editorial)

[View top submissions](/challenges/for-loop-in-c/leaderboard)

rate this challenge

MORE DETAILS

* * *

[Download problem statement](/rest/contests/master/challenges/for-loop-in-c/download_pdf?language=English)

[Download sample test cases](/rest/contests/master/challenges/for-loop-in-c/download_testcases)

Suggest Edits

Share on FacebookShare on TwitterShare on LinkedIn

-   [Blog](//blog.hackerrank.com)
-   [Scoring](/scoring)
-   [Environment](/environment)
-   [FAQ](/faq)
-   [About Us](//www.hackerrank.com/aboutus)
-   [Support](//help.hackerrank.com/hc/en-us)
-   [Careers](//www.hackerrank.com/careers)
-   [Terms Of Service](/terms-of-service)
-   [Privacy Policy](/privacy)
-   [Request a Feature](/support/feature)
