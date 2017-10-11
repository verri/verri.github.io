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

Thus, we can call an arbitrary function `do_something` for each integer between
0 (inclusive) and 10 (non-inclusive) by using
```cpp
for (int i = 0; i < 10; ++i)
  do_something(i);
```

We can also use for loops to iterate over containers.

```cpp
std::vector<int> values( /* ... */ );

for (typename std::vector<int>::iterator it = values.begin();
     it != values.end();
     ++it)
{
  do_something(*it);
}
```

For a better review, I suggest reading [this page](http://en.cppreference.com/w/cpp/language/for).

## C++11 range-based for loops

Modern C++ revisions (after C++11) bring a much better way to iterate over
containers: the range-based for loops.

The last piece of code is equivalent to
```cpp
std::vector<int> values( /* ... */ );

for (int i : values)
  do_something(i);
```

For a better review, I suggest reading [this page](http://en.cppreference.com/w/cpp/language/range-for).

## Problem: Value range

## Problem: Iterating two containers

## Solution: cool::indices utility
