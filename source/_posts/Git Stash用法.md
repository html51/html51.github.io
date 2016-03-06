title: Git Stash用法
date: 2016-01-25 21:13:45
categories:
- GIT
tags: [GIT]

---

> * **git stash**：备份当前的工作区的内容，从最近的一次提交中读取相关内容，让工作区保证和上次提交的内容一致。同时，将当前的工作区内容保存到Git栈中。
> * **git stash pop**：从Git栈中读取最近一次保存的内容，恢复工作区的相关内容。由于可能存在多个Stash的内容，所以用栈来管理，pop会从最近的一个stash中读取内容并恢复。
> * **git stash list**：显示Git栈内的所有备份，可以利用这个列表来决定从那个地方恢复。
> * **git stash clear**：清空Git栈。

#### **Git Stash用法操作流程--暂存分支**
> 这里的分支自己根据项目的实际情况来操作，所以知道流程才是主要的。
``` javascript
git status                      ###查看分支状态，当前状态是正在修改的分支，可以看到修改过的文件
                                ###当前分支为：@newdevelop
git stash                       ###暂存当前正在修改的分支
git status                      ###查看分支状态，当前分支修改过的文件没有了
git checkout develop            ###切换马上修改的新分支
git status                      ###查看马上修改的分支状态
```
#### **Git Stash用法操作流程--恢复暂存分支**
> bug修复之后，现在我们切换到newdevelop分支继续上次修改
``` javascript
git checkout newdevelop         ###切换到上次修改的分支继续修改文件
git status                      ###查看当前分支状态，可以看到修改过的文件，并没有出现，接下来要恢复暂存分支
git stash pop                   ###恢复暂存分支
git status                      ###查看当前分支状态，出现了上次修改过的文件，，接下我们就可以继续修改当前分支了
```

