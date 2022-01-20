### 1. `git push`
这里其实是一种简写，完整的写法是这样的
`git push <远程主机> <本地分支>:<远程分支>`
`当远程分支被省略，则推送到和本地分支同名的远程分支，如果没有则创建`
这里推送本地master分支到远程master分支
```shell
git push origin master
```
远程仓库有时是有分支的，我们需要把代码推送到指定分支
```shell
git push origin master:dev
或者
git push origin dev:master
```
更多操作:[git push](https://chinese.freecodecamp.org/news/git-push-to-remote-branch-how-to-push-a-local-branch-to-origin/)
