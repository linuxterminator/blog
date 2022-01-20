### 1. `git remote`
1. `git remote add`
2. `git remote -v`
3. `git remote show`
4. `git remote remove`
5. `git remote push`
6. `git remote rename`
8. `git remote set-url`

> 更多命令请查看`man git-remote`

#### 1.1 添加远程仓库
首先，我们需要添加远程仓库的地址
```shell
git remote add name url 
```

例如
```shell
git remote add pb https://github.com/paulboone/tic.git
```

#### 1.2 查看远程仓库
查看远程仓库使用如下命令
```shell
git remote -v
```

上面的命令会显示所有的`远程仓库`和`url`，如下
```shell
gitea_blog	http://101.34.170.88:3000/LinuxTerminator/blog.git (fetch)
gitea_blog	http://101.34.170.88:3000/LinuxTerminator/blog.git (push)
```

但是，我们无法看到仓库的详细信息，不过，我们可以使用如下命令查看
```shell
git remote show name
```

会显示如下信息
```shell
* remote github_blog
  Fetch URL: https://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@github.com/linuxterminator/LenMoreBlog.git
  Push  URL: https://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@github.com/linuxterminator/LenMoreBlog.git
  HEAD branch: master
  Remote branches:
    dev    tracked
    master new (next fetch will store in remotes/github_blog)
  Local refs configured for 'git push':
    dev    pushes to dev    (up to date)
    master pushes to master (local out of date)
```

#### 1.3 删除远程仓库
删除远程仓库
```shell
git remote remove name
```

#### 1.4 修改远程仓库
重命名
```shell
git remote rename old-name new-name
```

修改远程仓库的url
```shell
git remote origin set-url url
```

