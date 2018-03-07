---
title: HTTP的请求与响应
date: 2018-03-02 20:44:37
tags:
---
> 对于浏览器访问网站的过程中发生的请求与响应的相关知识

### 浏览器与服务器是如何沟通的
- 浏览器负责发起请求
- 服务器在 80 端口接收请求
- 服务器负责返回内容（响应）
- 浏览器负责下载响应内容
- HTTP 的作用就是指导浏览器和服务器如何进行沟通。

<!-- more -->

### 简单请求示例及格式讲解
- GET请求
` curl -s -v -H "Hello: http" -- "https://www.baidu.com " `

![用 curl 创造一个GET请求，并得到响应](http://upload-images.jianshu.io/upload_images/2244949-9ee938da26b7d7e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


请求的内容为
```
GET / HTTP/1.1
Host: www.baidu.com
User-Agent: curl/7.54.0
Accept: */*
Hello: http
```

-  POST请求
`curl -X POST -d "1234567890" -s -v -H "Hello: xxx" -- "https://www.baidu.com"`

![用 curl 创造一个POST请求，并得到响应](http://upload-images.jianshu.io/upload_images/2244949-f822643562f8843e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

请求的内容为
```
POST / HTTP/1.1
Host: www.baidu.com
User-Agent: curl/7.54.0
Accept: */*
Hello: xxx
Content-Length: 10
Content-Type: application/x-www-form-urlencoded

1234567890   /* 该部分内容在response里可见 */
```
- 请求的格式
```
1 动词 路径 协议/版本
2 Key1: value1
2 Key2: value2
2 Key3: value3
2 Content-Type: application/x-www-form-urlencoded
2 Host: www.baidu.com
2 User-Agent: curl/7.54.0
3 
4 要上传的数据
```
1. 请求最多包含四部分，最少包含三部分。（也就是说第四部分可以为空）
2. 第三部分永远都是一个回车（\n）
3. 动词有 GET POST PUT PATCH DELETE HEAD OPTIONS 等
4. 这里的路径包括「查询参数」，但不包括「锚点」
5. 如果你没有写路径，那么路径默认为 /
6. 第 2 部分中的 Content-Type 标注了第 4 部分的格式

### 响应示例及格式讲解
> 请求了之后，应该都能得到一个响应，除非断网了，或者服务器宕机了。

- 响应示例
```
HTTP/1.1 200 OK
Accept-Ranges: bytes
Cache-Control: private, no-cache, no-store, proxy-revalidate, no-transform
Connection: Keep-Alive
Content-Length: 2443
Content-Type: text/html
Date: Tue, 10 Oct 2017 09:14:05 GMT
Etag: "5886041d-98b"
Last-Modified: Mon, 23 Jan 2017 13:24:45 GMT
Pragma: no-cache
Server: bfe/1.0.8.18
Set-Cookie: BDORZ=27315; max-age=86400; domain=.baidu.com; path=/

<!DOCTYPE html>
<!--STATUS OK--><html> <head> 后面太长，省略了……
```
- 响应的格式
```
1 协议/版本号 状态码 状态解释
2 Key1: value1
2 Key2: value2
2 Content-Length: 17931
2 Content-Type: text/html
3
4 要下载的内容
```
1. 状态码很重要，是服务器对浏览器说的话
``1xx 不常用  这一类型的状态码，代表请求已被接受，需要继续处理。``
``2xx 表示成功 这一类型的状态码，代表请求已成功被服务器接收、理解、并接受。 ``
``3xx 表示滚吧 这类状态码代表需要客户端采取进一步的操作才能完成请求。通常，这些状态码用来重定向，后续的请求地址（重定向目标）在本次响应的Location域中指明。（一般来说就是搬家了）``
``4xx 表示你丫错了 这类的状态码代表了客户端看起来可能发生了错误，妨碍了服务器的处理。``
``5xx 表示好吧，我错了 表示服务器无法完成明显有效的请求。一般来说就是服务器宕机了。``
2. 状态解释没什么用
3. 第 2 部分中的 Content-Type 标注了第 4 部分的格式
4. 第 2 部分中的 Content-Type 遵循 MIME 规范

- 用 Chrome 查看响应
1. 打开 开发者工具-Network
2. 输入网址
3. 选中第一个响应
4. 查看 Response Headers，点击「view source」，点击「view source」，点击「view source」
5. 你会看到响应的前两部分，查看 Response 或者 Preview，你会看到响应的第 4 部分