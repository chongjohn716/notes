---
title: Hexo 同时提交到 Github 和 Coding
date: 2017-06-08 02:49:34
tags: Hexo, Github, Coding
---

---

**目的**: 将 `Hexo` 资源代码同时发布到 `Github` 和 `Coding`，通过 `Hexo` 的部署命令将静态文件部署到两个远程仓库的 `pages` 分支。

假设已经将本地代码发布到 `Github` 上，如果没有，参考这个文章来操作，[20分钟教你使用hexo搭建github博客](http://www.jianshu.com/p/e99ed60390a8)


## 创建 `Coding` 项目

在 `Coding` 上创建一个空项目，同时创建 `coding-pages` 分支，并将 `pages服务` 设置为 `coding-pages` 分支。

{% asset_img coding_branchs.png 创建 coding-pages 分支 %}
{% asset_img pages_setting.png 设置 coding-pages 到 pages 服务 %}


## 修改 `_config.yml` 配置

修改 `_config.yml` 配置的 `deploy` 项为如下：

```bash
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: 
      github: git@github.com:username/notes.git,gh-pages
      coding: git@git.coding.net:username/notes.git,coding-pages    # 注意这里的分支名不一样
```


## 修改 git config

修改项目目录下 `.git/config` 文件中的 `remote` 为如下，注意将 `remote` 后面参数改为 `all`。

```bash
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "all"]
	url = git@github.com:username/notes.git
	url = git@git.coding.net:username/notes.git
	fetch = +refs/heads/*:refs/remotes/origin/*
```

然后执行下面命令

```bash
git push all master
```



## 参考：
[有没有办法同步 Coding 与 GitHub](https://segmentfault.com/q/1010000000172591)
[hexo博客同时部署至github和Coding](http://blog.csdn.net/u011303443/article/details/51509351)





