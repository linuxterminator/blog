### 1. git log
使用`git log`来显示提交日志
> 关于更多的参数请查看[git log](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

更多参数请输入以下命令
```shell
man git-log
```

- `git log`
- `git log -p`
- `git log --stat`
- `git log --pretty=oneline`
- `git log --graph`
- `git --since`

#### 1.1 `git log`
使用`git log`可以查看提交的历史
```shell
commit f5ffb45fa6807654368dc79a6bc1b08d74acaa0d (HEAD -> dev, github_blog/dev)
Author: 胡青山 <linuxterminator@163.com>
Date:   Sun Sep 12 17:47:18 2021 +0800

    完善了错误处理，添加了参数验证错误处理，以及错误api封装，添加了aop支持

commit 49ffb45bbda5eb13c2f506217def72a7d50b7d67 (gitea_blog/master)
Author: 胡青山 <linuxterminator@163.com>
Date:   Mon Sep 6 17:18:44 2021 +0800

    参数验证和统一错误处理
```

> 此命令列出了每个提交及其 SHA-1 校验和、作者姓名和电子邮件、写入日期和提交消息。

#### 1.2 差异化显示
有时候，我们想要显示差异化，我们可以使用一些参数
```shell
git log -p

或者
git log --patch
```
它会在`git log`的基础上显示每一个提交的具体修改内容，就像`git diff`方便review

#### 1.3 查看每次提交的缩略信息
使用`git log --stat`，会帮我们显示每次提交的缩略统计
```shell

git log --stat

commit 959f56b814df778d8a5709e9d57df7e4ec46aee5
Author: 胡青山 <luolikong950412@163.com>
Date:   Fri Aug 20 21:32:56 2021 +0800

    第一个简单的提交，作为ci/cd测试使用

 .gitignore                                                        |  33 +++++++++++
 .mvn/wrapper/MavenWrapperDownloader.java                          | 117 +++++++++++++++++++++++++++++++++++++++
 .mvn/wrapper/maven-wrapper.jar                                    | Bin 0 -> 50710 bytes
 .mvn/wrapper/maven-wrapper.properties                             |   2 +
 mvnw                                                              | 310 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 mvnw.cmd                                                          | 182 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 pom.xml                                                           |  59 ++++++++++++++++++++
 /LenMore/LenMoreApplication.java      |  15 +++++
 /LenMore/controller/Article.java      |  19 +++++++
 /LenMore/controller/Login.java        |  19 +++++++
 /LenMore/controller/User.java         |  19 +++++++
 /LenMore/dao/Article.java             |  15 +++++
 /LenMore/dao/User.java                |  12 ++++
 src/main/resources/application.properties                         |   1 +
 /LenMore/LenMoreApplicationTests.java |  13 +++++
 15 files changed, 816 insertions(+)
```

#### 1.4 更改输出格式
`git log`可以有很多种输出格式，我们可以使用`pretty`来指定，不过一般只有如下几种比较常见
> 更多的说明符请查看[git --pretty=format](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History#pretty_format)

- `git --pretty=oneline`

同时查看大量的提交
```shell
git --pretty=oneline

f5ffb45fa6807654368dc79a6bc1b08d74acaa0d (HEAD -> dev, github_blog/dev) 完善了错误处理，添加了参数验证错误处理，以及错误api封装，添加了aop支持
49ffb45bbda5eb13c2f506217def72a7d50b7d67 (gitea_blog/master) 参数验证和统一错误处理
15fee1bc8b758f14a35ff5fc04872f4ddd15f485 统一错误处理，以及Optional，banner修改
6c8b84940e5951adf5f76cd1d56fc73228c90441 (gitea_blog/dev, master) 添加readme和增加一些美化
```

使用简写
```shell
git log --oneline
```

输出`ascii`图像
```shell
git --graph

* commit f5ffb45fa6807654368dc79a6bc1b08d74acaa0d (HEAD -> dev, github_blog/dev)
| Author: 胡青山 <linuxterminator@163.com>
| Date:   Sun Sep 12 17:47:18 2021 +0800
|
|     完善了错误处理，添加了参数验证错误处理，以及错误api封装，添加了aop支持
|
* commit 49ffb45bbda5eb13c2f506217def72a7d50b7d67 (gitea_blog/master)
| Author: 胡青山 <linuxterminator@163.com>
| Date:   Mon Sep 6 17:18:44 2021 +0800
|
|     参数验证和统一错误处理
|
* commit 15fee1bc8b758f14a35ff5fc04872f4ddd15f485
| Author: 胡青山 <linuxterminator@163.com>
| Date:   Thu Sep 2 16:50:20 2021 +0800
|
|     统一错误处理，以及Optional，banner修改
|
* commit 6c8b84940e5951adf5f76cd1d56fc73228c90441 (gitea_blog/dev, master)
| Author: 胡青山 <luolikong950412@163.com>
| Date:   Thu Aug 26 13:13:00 2021 +0800
|
|     添加readme和增加一些美化
|
```

#### 1.5 限制输出
按作者
```shell
git log --author="胡青山"
```