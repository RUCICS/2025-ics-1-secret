# Homework2

这是 [Homework2.pdf](https://github.com/RUCICS/2025-ics-1/blob/main/%E4%BD%9C%E4%B8%9A/Homework2/Homework2.pdf)的标准答案。

## Q1

| Value | Two’s complement |
|-------|------------------|
| 37    | 00100101         |
| -15   | 11110001         |
| 85    | 01010101         |
| -86   | 10101010         |

## Q2

| Expression | Binary Representation |
| ---------- | --------------------- |
| us         | 1101                  |
| ui         | 11001100              |
| us«1       | 1010                  |
| i»2        | 11110011              |
| ui»2       | 00110011              |
| short(i)   | 1100                  |
| (int)s     | 11111101              |

## Q3

```c
int uadd_ok(unsigned x, unsigned y) 
{
unsigned sum = x+y;  
if(sum < x && sum < y)  
 return 1;
else return 0;

}

#include <limits.h>  
int uadd_ok(unsigned x, unsigned y):
{
return (x > UINT_MAX - y); 
}

```
