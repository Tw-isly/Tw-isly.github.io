---
title: C++ 速记：memcpy 的长度单位是字节
date: 2026-09-28
tags:
  - C++
categories:
  - 编程学习
---

`memcpy` 的第三个参数是**字节数**，不是元素个数。

```cpp
memcpy(b, a, 10);  // 错：只复制 10 bytes
```

常见环境中 `int` 占 4 bytes，因此这不等于复制 10 个 `int`。出现 `1 2 3 0 0...` 与内存布局及小端存储有关，不应依赖。

```cpp
memcpy(b, a, sizeof(a));  // 复制整个数组
```

记忆：`memcpy(目标, 来源, 字节数)`。
