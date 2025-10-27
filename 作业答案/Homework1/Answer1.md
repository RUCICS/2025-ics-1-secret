# Homework1

这是 [Homework1.pdf](https://github.com/RUCICS/2025-ics-1/blob/main/%E4%BD%9C%E4%B8%9A/Homework1/Homework1.pdf)的标准答案。

## Q1

| Binary          | Octal | Decimal | Hexadecimal |
|-----------------|-------|---------|-------------|
| 101 0101 0110   | 2526  | 1366    | 0x556       |
| 1 1111 1111     | 777   | 511     | 0x1FF       |
| 1 1100 0101     | 705   | 453     | 0x1C5       |
| 111 1101 1111   | 3737  | 2015    | 0x7DF       |
| 100 0000 1101   | 2015  | 1037    | 0x40D       |

## Q2

A = 0x7F = 0111 1111;
B = 0xBA = 1011 1010;
(a)A & B = 0011 1010 = 0x3A;
(b)A | B = 1111 1111 = 0xFF;
(c)A ^ B = 1100 0101 = 0xC5;
(d)~A|~B = ~(A & B) = 1100 0101 = 0xC5;
(e)A &&B = true;
(f)A ||B = true;

## Q3

(a)!(~x);
(b)!x;
(c)x & 0xff;
(d)!(x & 0xff);

## Q4

> 注意使用32位掩码

(x & 0x0000ffff) + (y & 0xffff0000);
