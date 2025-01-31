---
title: git基本概念
type: tools
---

## #git 基本概念
### HEAD
这是当前分支版本顶端的别名，也就是在当前分支你最近的一个提交
注：另有detach状态：[[head-detached]]
### Index
index也被称为staging area，是指一整套即将被下一个提交的文件集合。他也是将成为HEAD的子节点的那个commit
注：如果在[[head-detached]]，就有可能“产生新的（临时）分支”
### Working Copy
working copy代表你正在工作的那个文件集

### 操作过程
(https://www.cnblogs.com/kidsitcn/p/4513297.html)
- 当你第一次checkout一个分支，HEAD，Index，Working Copy都相同
- 当你对一个文件执行一次修改（比如编辑器打两行字然后`Ctrl + S`保存），Git感知到了这个修改，并且说：“嘿，文件已经变更了！你的working copy不再和index,head相同！”，随后GIT标记这个文件是修改过的。
可以理解成`git`相当于比文本编辑器“高一层”，是“文件夹编辑器”。这里的修改相当于“文本没保存”
- 然后，当你执行一个git add,它就stages the file in the index，并且GIT说：“嘿，OK，现在你的working copy和index区是相同的，但是他们和HEAD区是不同的！”
这里类比文本编辑器的按保存。
- 当你执行一个git commit,GIT就创建一个新的commit，随后HEAD就指向这个新的commit，而index,working copy的状态和HEAD就又完全匹配相同了，GIT又一次HAPPY了。
- 以上都在本地进行。如果要远程，则再`pull`和`push`. 类比文本编辑器的传递上云