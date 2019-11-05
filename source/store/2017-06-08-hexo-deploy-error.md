---
title: 执行 hexo -d 时报错
date: 2017-06-08 21:57:14
tags: Memo, Hexo
---

---

## 问题描述

执行 `hexo -d` 时，出现下面错误

```shell
ERROR Deployer not found: git
```

{% asset_img d_error.png ERROR Deployer not found: git %}

## 解决方法

安装 `hexo-deployer-git` 插件

```bash
npm install hexo-deployer-git --save
```

{% asset_img install_d_git.png npm install hexo-deployer-git --save %}

