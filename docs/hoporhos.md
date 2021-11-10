---
layout: default
title: HOP OR HOS
nav_order: 3
---

# HOP or HOS
{: .no_toc }



{: .fs-6 .fw-300 }



## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## A guide for doing HOP or HOS on GitHub.




## How to organize your HOP/HOS repository for class?

We have 10 weeks every quarter. For doing homework, we will always download files or clone repository from GitHub. A recommended file structure is below. We will create 10 weeks folder under the course.

For example, we will create a folder for every course by course number. Every quarter has 10 weeks, so we create 10 folders follow the "ModuleXX" formatation.

![HOP and HOS organized sturcture](/assets/images/hops_organized_sturcture.png)

## How to submit your work to GitHub?


There're 2 typical ways to submit your work to GitHub. 

### Git Command Line

```bash
cd {your_repo_path}
git add .
git commit -m 'Submission for Module{0X} - {Your name}'
git push origin main
```

#### Example

```bash
❯ git add .
❯ git commit -m 'Submission for Module06 - Wenzhi Xu'
[main 93e1062] Submission for Module06 - Wenzhi Xu
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .DS_Store
❯ ggpush
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 591 bytes | 591.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:cityuseattle/IS440-HOP06-Fall-2021.git
   91edf39..93e1062  main -> main
```




### GitHub Desktop.


... TODO