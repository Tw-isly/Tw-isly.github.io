---
title: C++ 中读取以 0 结束的一串整数：三种 while 写法
date: 2026-09-21 12:48:08
tags:
  - C++
  - 循环
categories:
  - 编程学习
---

输入一串整数，以 `0` 结束（`0` 不参与处理）。

### 1. while 条件中读入（推荐）

```cpp
int x;
while (cin >> x && x != 0) {
    // 处理 x
}
```

### 2. while + break

```cpp
int x;
while (true) {
    if (!(cin >> x) || x == 0) break;
    // 处理 x
}
```

### 3. do...while

```cpp
int x;
do {
    cin >> x;
    if (x != 0) {
        // 处理 x
    }
} while (x != 0);
```

选择：一般用 1；退出条件复杂时用 2；必须先执行一次时用 3。
