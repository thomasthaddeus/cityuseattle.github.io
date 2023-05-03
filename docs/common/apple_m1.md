---
layout: default
title: Are you using Apple Silicon?
parent: Common Solutions
---

Apple released Apple Silicon (M1) or other later version in the end of 2020. The big thing is that Apple changed their chip architecture from Intel to ARM. Some software is not developed for compatibility.

To check if you're using Apple Silicon, follow the instructions below.

* Click the Apple icon in the top-left corner.
* Click "About this Mac"

![applem1](/assets/images/common/apple_m1/applem1.png)

If the Chip is "Apple M1", that means you're using Apple Silicon. Some software may no longer be compatible, even on virtual machines. This is because the underlying architecture is different. All programming languages used to make software must be compiled to supported machine languages, which are unique to architectures. Intel and AMD architectures are very similar, so the overwhelming of desktop/laptop software will work on these machines. However, moving to an ARM-based custom architecture as Apple did with the Mac line messes this all up. Few of the compilers (yet) support the corresponding machine language.

This necessitates finding novel solutions. In the future, the school may implement Amazon EC2 instances which virtually runs environments apart from the student's computer. Therefore you would only need an internet connection, and everything from there is agnostic and apathetic to your underlying hardware. For now, let's look at what local virtual machine solutions exist.

## 1) Parallels

Parallels is probably the best all-around solution, with the significant caveat that it is not free, and is arguably pretty expensive.
