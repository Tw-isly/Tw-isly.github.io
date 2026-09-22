---
title: C++ 速记：scanf 与无临时变量交换
date: 2026-09-21
tags:
  - C++
categories:
  - 编程学习
---

### 1. scanf 输入普通变量要加 `&`

```cpp
int x;
scanf("%d", &x);
```

`scanf` 需要变量的地址。

### 2. scanf 不能直接读取 string

```cpp
char s[100];
scanf("%99s", s);  // 数组名本身就是地址，不加 &
```

`std::string` 使用 `cin >> s`。

### 3. 不用临时变量交换两个整数

```cpp
a = a + b;
b = a - b;
a = a - b;
```

常见环境中两个 `int` 共 8 bytes，无需额外变量；加法可能溢出，实际代码优先使用 `swap(a, b)`。
