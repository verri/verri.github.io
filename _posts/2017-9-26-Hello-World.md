---
layout: post
title: Hello World!
---

Since I started researching on machine learning and dynamical systems,
I have been developing several utility libraries.
Most of them are written in modern C++ because of its flexibility and performance.

In this blog, I intend to write my thoughts on machine learning and C++ programming.
Specifically, I will discuss the motivation and the design decisions of the C++ libraries I have been developing:
[Jules](https://github.com/verri/jules) and [Cool](https://github.com/verri/cool).

## Jules

Without question, *Jules* is my favorite.

I started writing it to overcome several inconveniences I had with other frameworks.
My first research experiments (back in 2011) were written in Matlab.
At the time, speed and flexibility were not a problem, since the problems were simple.
Then, at some point, I decided to try R.
I liked the flexibility and the huge amount of available packages which drastically increased my productivity.
However, at the beginning of my PhD, I had many problems with the hard maintenance of code.
Every time I would update R, I would need to make few (but annoying) changes in the code because of the many dependencies I had.
Since I wasn't happy with the performance either and
I had just finished reading [the 4th edition of The C++ Programming Language](http://www.stroustrup.com/4th.html),
I decided to write my own framework to deal with statistical programming using modern C++.

Most of my studies comprise only some kind of dynamical system simulation,
thus a library with basic array manipulation and statistical utilities (sum, mean, standard deviation, etc) would suffice.
There are some other C++ libraries out there that provide such functionalities.
[Blaze](https://bitbucket.org/blaze-lib/blaze) and [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page) are
good examples.
However, I had some reasons to create *yet another (TM)* library:

- *Modern C++*. Jules is not intended to work in old compilers, so I can use the most recent features of C++.
- *Productivity over speed*. Most of the related C++ libraries are blazing fast and highly configurable,
  but they are hard to learn and decrease a lot your productivity.  Jules, in the contrary, aims at
  being simple and intuitive, without many configuration options.  Moreover, it is header-only, which
  should help integration in your project.
  **Besides Jules focusing in flexibility and simplicity, it doesn't mean that it is slow.**
  Soon, I should run some benchmarks and post them here.

[Paulo Urio](https://github.com/jimmyskull) and I started writing it in June 2015.
Since then, the library has been evolving in a good pace, taking it in mind that there are only 2 contributors.
The library is not stable yet, but I have been using it in every one of my projects.
Most of the features I have implemented are directly connected with my needs,
but if you intend to use it and need some feature, [fill an issue](https://github.com/verri/jules/issues) that
I will gladly try to implement it.

I will eventually blog about Jules and its usage.

## Cool

One problem that I have every time I start a new project is that I see myself reimplementing some simple
functionalities.  Instead of doing so, or using [Boost](http://www.boost.org/), I decided to aggregate
many simple tools into a single project.  *Cool* aims at providing:

- *Easy integration*: Every functionality is implemented in a single header file with just a couple hundred lines.
- *Productivity over flexibility*: Unlike Boost, utilities are not heavily templated or configurable.

Many of my posts here will discuss the rationale and the design decisions of the parts of Cool.
I will focus on the usage of modern C++ features.
