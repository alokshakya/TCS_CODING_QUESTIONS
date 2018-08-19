# TCS_CODING_QUESTIONS

In TCS 2017 campus placement, first round has introduced new pattern. This year onward, the test shall consist of 4 sections, instead of the earlier two. The duration, however, shall remain the same, i.e. 90 minutes. The details are:

* ### Verbal Test (10 Mins) :
In this you have to write email in 10 minutes.

* ### Quantitative Test (40 Mins) :
This section will have only 20 questions from aptitude.

* ### Test on Programming Language Proficiency (20 Mins) :
This section shall have MCQ based questions related to basic programming concepts (on C language).

* ### Coding Test (20 Mins) :

This section shall require the student to solve a coding problem real time using an in built compiler (on C Language).

To solve this 4th section you can’t use keywords like “scanf, getc, getch, getchar” so to solve this type of coding problem. You have to use input from ***command line arguments***.

## Now Programs

* ## Problem Statement :

> *Write a C program to calculate the factorial of a non negative integer N. The factorial of a number N is defined as the product of all integers from 1 up to N. Factorial of 0 is defined to be 1. The number N is a non negative integer that will be passed to the program as the first command line parameter. Write the output to stdout formatted as an integer WITHOUT any other additional text. You may assume that the input integer will be such that the output will not exceed the largest possible integer that can be stored in an int type variable*.

**Example :** 
```
If the argument is 4, the value of N is 4. 
So, 4 factorial is 1*2*3*4 = 24.
Output : 24
```
### Solution

```c
#include<stdio.h>
#include<stdlib.h>
int fact(int n)
{
    if(n==0) return 1;
    else
    {
        int i;
        int ans=1;
        for(i=1;i<=n;i++)
            ans=ans*i;
        return ans;
    }
}
int main(int argc, char *argv[])
{
    if(argc==1)
    {
        printf("No Arguments Provided\n");
        return 0;
    }
    else
    {
        int n;
        n=atoi(argv[1]);
        int factorial;
        factorial=fact(n);
        printf("%d\n",factorial);
        return 0;
    }
}
```

### Now description of code :

`#include <stdio.h>` *// is used for printf function*

`#include <stdlib.h>` *//is used for function atoi() and atoi is used converting string into int*

**You may be asked to take float input from command line so in that case you have to use** ***atof()*** **function which is also present in `#include<stdlib.h>` atof() is a function in the C programming language that converts a string into a floating point numerical representation.**

**// argc tells the number of arguments provided+1,  +1 for file.exe** suppose you will be provided 1 input n from command line then value of argc would be 2. One for input n and another for file.exe.

**// `char* argv[]` is used to store the command line arguments in the string format**

`int main(int argc, char* argv[])` this line is important because in program you have to write this line if you would be taking input from command line arguments. Meaning of int argc and char* argv[] have been provided above.

`if(argc==1)` means you have not been provided any command line arguments. And value of argc==1 because file.exe will be provided automatically by compiler. So this line is written for exception handling while you are testing your program. If you are sure that input from command line arguments will be provided then you can remove this part. In TCS exam you will be provided input so you can remove if part and can start from else part.

**actual arguments starts from index 1 to (argc-1)** In this program we are provided that we will be provided only one number from command line argument. So we can directly access that number ***argv[1]***, remember argv[] is array of character types so we are accessing element at index 1. So this is string and we can't perform mathmatical operations on string.

**so for converting string into int we will use** ***atoi()*** **functioin which is predefined function in #include<stdlib.h>**

**Now `int n; n=atoi(argv[1])`** will provide n int on which we can perform operations. Just like taking input from scanf.

**You may be asked to take input of two numbers from command line arguments, then you declare two variables `int n,m;` and take input from command line as** `n=atoi(argv[1]); m=atoi(argv[2])` .

```c
int n,m;
n=atoi(argv[1]);
m=atoi(argv[2]);
```
`int factorial;` defining int variable factorial
`factorial = fact(n);` ***fact(n)*** is a function which returns int value which is factorial of a number.

```c
int fact(int n)
{
    if(n==0) return 1;
    else
    {
        int i;
        int ans=1;
        for(i=1;i<=n;i++)
            ans=ans*i;
        return ans;
    }
}
```
**You may define your own logic function**

**printf("%d\n",factorial);** is used to print result. `printf()` is defined inside #include <stdio.h>

This was description of whole code. Now you can write short version of above code for writing in **TCS EXAM**

```c
#include<stdio.h>
#include<stdlib.h>

int main(int argc, char *argv[])
{
    int n;
    n=atoi(argv[1]);
    int factorial=1;
    int i=0;
    for(i=1; i<=n; i++)
      {
        factorial = factorial*i; 
      }
    printf("%d\n",factorial);
    return 0;   
}
```

**Now we will write problem statement and solution for them, approach of solving them will be same, so description of code will not be provided. You will understand code easily.**

* ## Problem
> *Write a C program to calculate the area of a circle. You will be provided radius of circle as N. The number N is a non negative integer that will be passed to the program as the first command line parameter. Write the output to stdout formatted as an float upto 2 decimal places WITHOUT any other additional text. You may assume that the input integer will be such that the output will not exceed the largest possible integer that can be stored in an int type variable*.

**Example :** 
```
If the argument is 4, the value of N is 4. 
So, area of radius 4 is 3.14*4*4 = 50.24.
Output : 50.24
```
### Solution

```c
#include<stdio.h>
#include<stdlib.h>
int main(int argc, char * argv[])
{
    if(argc==1)
    {
        printf("No arguments");
        return 0;
    }
    else
    {
        int radius;
        float pi=3.14;
        float area;
        radius=atoi(argv[1]);
        area=pi*radius*radius;
        printf("%.2f",area);
        return 0;
    }
}
```


* ## Problem
> *Write a C program to calculate the area of a triangle. You will be provided base and height of triangle as N,M. The numbers N,M are non negative integer that will be passed to the program as the first and second command line parameter. Write the output to stdout formatted as an float upto 2 decimal places WITHOUT any other additional text. You may assume that the input integer will be such that the output will not exceed the largest possible integer that can be stored in an int type variable*.

**Example :** 
```
If the first argument is 4 and second argument is 3 the value of N is 4 and value of M is 3 
So, area of triagnle having base 4 and height 3 is 0.5*4*3 = 6.00.
Output : 6.00
```
### Solution

```c
#include<stdio.h>
#include<stdlib.h>
int main(int argc, char * argv[])
{
    if(argc==1)
    {
        printf("No arguments");
        return 0;
    }
    else
    {
        int base,height;
        float area;
        base=atoi(argv[1]);
        height=atoi(argv[2]);
        //area=(1/2)*base*height;//this formula will give answer 0.00 because (1/2) will give 0 because both 1 and 2 are int
        area=(1.0/2.0)*base*height;
        printf("%.2f",area);
        return 0;
    }
}
```

* ## Problem
> *Write a C program to calculate the square root of prime number N if N is not prime then print 0.00. Print the output upto 2 decimal places. The number N is a non negative integer that will be passed to the program as the first command line parameter. Write the output to stdout formatted as an integer WITHOUT any other additional text. You may assume that the input integer will be such that the output will not exceed the largest possible integer that can be stored in an int type variable*.

**Example :** 
```
If the argument is 5, the value of N is 5. 
Since 5 is a prime no so we have to print square root of 5 that is 2.2360679775, but we have to print upto 2 decimal places so we will print 2.23
Output : 2.23

If the argument is 4, the value of N is 4. 
Since 4 is not a prime no so we have to print 0.00
Output : 0.00

```
### Solution


```c
#include<stdio.h>
#include<stdlib.h>
#include<stdbool.h>
#include<math.h>
bool isPrime(int n)
{
    if(n<2)
        return false;
    int i;
    for(i=2;i*i<=n;i++)
    {
        if(n%i==0)
            return false;
    }
    return true;
}
int main(int argc, char *argv[])
{
    if(argc==1)
    {
        printf("No arguments");
        return 0;
    }
    else
    {
        int n;
        n=atoi(argv[1]);
        float sq=0;
        if(isPrime(n))
        {
            sq=sqrt(n);
            printf("%.2f",sq);
        }
        else
            printf("%.2f",sq);
        return 0;
    }
}
```

* ## Problem
> *Write a C program to print the **N**th fibonacci term of N. The number N is a non negative integer that will be passed to the program as the first command line parameter. Write the output to stdout formatted as an integer WITHOUT any other additional text. You may assume that the input integer will be such that the output will not exceed the largest possible integer that can be stored in an int type variable*.

**Example :** 
```
If the argument is 5, the value of N is 5. 
So we have to print 1+1+2+3+5 = 11
Output : 11

```
### Solution

```c
#include<stdio.h>
#include<stdlib.h>
int fib(int n)
{
    int a=0,b=1,c,i;
    if(n==0) return a;
    for(i=2;i<=n;i++)
    {
        c=a+b;
        a=b;
        b=c;
    }
    return b;
}
int main(int argc, char * argv[])
{
    if(argc==1)
    {
        printf("No arguments");
        return 0;
    }
    else
    {
        int n;
        n=atoi(argv[1]);
        printf("%d",fib(n));
        return 0;
    }
}
```
