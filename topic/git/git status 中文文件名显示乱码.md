---
title: "git status 中文文件名显示乱码"
date: 2022-09-17
tags:
- git技巧
---

## 问题描述
git 仓添加中文文件名后，`git status` 显示乱码，很不友好。

## 解决方法
设置 git 的 `core.quotepath` 选项为 `false` ：
```bash
git config --global core.quotepath false
```

## 问题详情
目录下有名为 `中文.md` 的测试文件，`git status` 查看显示如下：
```bash
baibaoxiang@MacBook-Pro content % git status 
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	"\344\270\255\346\226\207.md"
```

原因是 git 默认情况下会对字符编码大于 0x80 的进行 quote，如下是 [git 官网 quotePath 选项说明](https://git-scm.com/docs/git-config#Documentation/git-config.txt-corequotePath)

> core.quotePath
	Commands that output paths (e.g. _ls-files_, _diff_), will quote "unusual" characters in the pathname by enclosing the pathname in double-quotes and escaping those characters with backslashes in the same way C escapes control characters (e.g. `\t` for TAB, `\n` for LF, `\\` for backslash) or bytes with values larger than 0x80 (e.g. octal `\302\265` for "micro" in UTF-8). If this variable is set to false, bytes higher than 0x80 are not considered "unusual" any more. Double-quotes, backslash and control characters are always escaped regardless of the setting of this variable. A simple space character is not considered "unusual". Many commands can output pathnames completely verbatim using the `-z` option. The default value is true.

`core.quotePath` 设置为 `false` 后，效果如下：
```bash
baibaoxiang@MacBook-Pro content % git status 
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	中文.md
```

## 扩展阅读：
- [Git - git-config Documentation](https://git-scm.com/docs/git-config#Documentation/git-config.txt-corequotePath)

