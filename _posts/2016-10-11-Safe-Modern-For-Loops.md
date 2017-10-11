---
layout: post
title: Safe modern for loops
---

I had the opportunity to accompany many students while they were learning C.
Looking at their coding style, I noticed some bad habits that could lead to
hard-to-detect bugs in real-world problems. I'll show the tools that Modern C++
brings that can prevent that kind of problems.

## Pre-C++11 for loops

Before discussing the problems themselves, let's review how for loops work in C++.

In a very basic way, the code
```cpp
for (/* init_statement */; /* condition */; /* iteration_expression */) {
  /* statement */
}
```
is translated to
```cpp
{
  /* init_statement */;
  while ( /* condition */ ) {
    /* statement */
    /* iteration_expression */;
  }
}
```

## C++11 range-based for loops

## Problem: Iterating two containers

## Solution: Iterating two containers
