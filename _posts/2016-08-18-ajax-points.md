---
layout: post
title: "Ajax知识点"
keywords: ["Ajax","JavaScript","异步"]
description: "Ajax知识点一览"
category: "JavaScript"
tags: ["Ajax","JavaScript"]
---
{% include JB/setup %}

##Ajax概念

###同步

![](http://cdn.saymagic.cn/o_1ar5cmgh31ofl58ep9nnqvnf39.jpg)

###异步

![](http://cdn.saymagic.cn/o_1ar5cnifc1icuhu81ulqs5l19goj.jpg)

###XMLHttpRequest对象

<pre>
var request;
if (window.XMLHttpRequest) {
    //IE7+,FF,Chrome,Opera,Safari
    request = new XMLHttpRequest();
} else {
    //IE5,IE6
    request = new ActiveXObject("Microsoft.XMLHTTP");
}
</pre>

###HTTP请求

HTTP 是无状态的协议（即服务端不保留连接的相关信息，无记忆）。

一个完整的 HTTP 请求包含以下步骤：

1. 建立 TCP 连接
2. Web 浏览器向 Web 服务器发送请求命令
3. Web 浏览器发送请求头信息
4. Web 服务器做出应答
5. Web 服务器发送应答头信息
6. Web 服务器向浏览器发送数据
7. Web 服务器关闭 TCP 连接

HTTP 请求的组成：

1. 请求的方法或动作，GET（一般用于信息的获取，查询） | POST（信息的修改、新建）
2. 正在请求的 URL，即请求的地址
3. 请求头，包含客户环境信息、身份验证信息等
4. 请求体，即请求正文，可包含用户提交的查询字符串、表单信息等（请求头和请求体之间会有一个空行）

HTTP 响应的组成：

1. 一个数字和文字组成的状态码，用于显示请求成功还是失败
2. 响应头，包含服务器类型、日期时间、内容类型等服务器相关信息
3. 响应体，即响应正文

HTTP 状态码由三位数字构成，首位数字定义了状态码的类型：

`1XX`：信息类，表示收到 Web 浏览器的请求，正在进一步处理中

`2XX`：成功，表示用户请求被正确接收、理解、处理，如 200 OK

`3XX`：重定向，表示请求未成功，客户必须采取进一步动作

`4XX`：客户端错误，表示客户提交的请求有误，如 404 Not Found

`5XX`：服务器错误，表示服务器不能完成对请求的处理，如 500