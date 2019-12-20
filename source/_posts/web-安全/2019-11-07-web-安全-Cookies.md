---
title: Web 安全 --- Cookies
date: 2019-11-07 23:00:28
categories:
- Web 安全
- 笔记
tags: 
- Web 安全
- Cookies
---

## 特性

1. 浏览器数据存储
2. 服务端可通过 http 头设置
3. 请求时通过 http 头传递
4. 前端可读写 (`http-noly`不能读取)
5. 同源策略

## 属性

1. name
2. value
3. domain
4. expires
5. path
6. http-only
7. secure
8. same-site

**通过设置 `cookie` 的有效期来删除**

## 登录用户凭证

1. 用户ID + 签名
2. SessionId

## 与 XSS

XSS 可能盗取 cookies, 冒充用户身份, 设置 `http-only` 看防御

## 与 CSRF

利用 cookies 发起请求, 无法读写 cookies

## 安全策略

1. 签名防篡改
2. 加密
3. http-only (防止 XSS)
4. secure
5. same-site (防止 CSRF)
