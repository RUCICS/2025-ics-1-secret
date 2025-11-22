# Homework4

这是 [Homework4.pdf](https://github.com/RUCICS/2025-ics-1/blob/main/%E4%BD%9C%E4%B8%9A/Homework4/Homework4.pdf)的标准答案。

## Answer1(1)

|Operand | Value|
|--------|-----|
|%ebx| 0x100 |
|$0x150| 0x150 |
|0x170| 0x17 |
|(%ebx)| 0x10 |
|(%ebx,%eax)| 0x11 |
|0x30(%ebx)| 0x13 |
|80(%ebx,%eax,2)| 0x17 |

## Answer1(2)

| Instruction | 目标(Destination) | 值(Value) |
| ----------- | ---------- | ----- |
|addl %eax,%ebx | %ebx | 0x110 |
|subl %eax,(%ebx) | (%ebx) 或 0x100 | 0x0 |
|leal 0x50(%eax), %edx | %edx | 0x60 |
|movzbl %al, %ebx | %ebx | 0x10 |
|movsbl %bh, %ecx | %ecx | 0x1 |

## Answer1(3)

| Instruction | OF | SF | ZF | CF|
| ----------- | -- | -- | -- | -- |
|leal(%eax),%ebx| 0 | 0 | 0 | 0 |
|subl %ebx, %eax| 0 | 1 | 0 | 1 |
|xorl %eax, %eax| 0 | 0 | 1 | 0 |
|test %eax, %ebx| 0 | 0 | 1 | 0 |

## Answer2

```c
int func(int x, int y) {
    // 8(%ebp) -> x
    // 12(%ebp) -> y
    // -4(%ebp) -> 局部变量, 命名为 a
    // -8(%ebp) -> 局部变量, 命名为 b
    // -12(%ebp) -> 局部变量, 命名为 c
    
    int a, b, c;

    c = x;  // movl %eax, -12(%ebp) (c 未被使用)
    b = y;  // movl %edx, -8(%ebp)
    a = 1;  // movl $1, -4(%ebp)
    
    // .L2 (循环条件检查)
    // testl %eax, %eax (b > 0?)
    // jg .L3 (如果 b > 0, 跳转到 .L3)
    while (b > 0) {
        // .L3 (循环体)
        a = a + b; // addl %eax, %edx; movl %edx, -4(%ebp)
        b = b - 1; // subl $1, -8(%ebp)
    }

    return a; // movl -4(%ebp), %eax
}
```
