- url param

```
http://guang.zxg/person/1111
```

111就是url param。服务端框架或者单页应用的路由都支持从url中取参数。

- query

```
http://guang.zxg/person?name=guang&age=20
```

name和age是query传递的数据。

其中非英文的字符和一些特殊字符要经过编码，可以使用 encodeURIComponent 的 api 来编码：

```
const query = "?name=" + enCodeURIComponent('光') + "&age=20"

// ?name=%E5%85%89&age=20
```

- form-urlencoded

直接用form表单提交数据就是这种，他和 query 字符串的方式的区别就是只是放在body里，然后指定下 content-type 是 application/x-www-form-urlencoded

```
POST /dddd HTTP/1.1
User-Agent: PostmanRuntime/7.28.4
Accept: */*
Postman-Token: e23a8dab-13b2-4a17-a7ce-14dbca01a701
Host: localhost:3000
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 21
Connection: keep-alive

name= %E5%85%89&age=22
```

- form-data

form data 不再是通过 & 分隔数据，而是用 --------- + 一串数字作为 boundary 分隔符。因为不是 url 的方式了，自然也不用再做 url encode。

- json

用于传输json数据