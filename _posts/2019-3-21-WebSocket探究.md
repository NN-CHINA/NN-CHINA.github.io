---
title: WebSocket探究
categories: WebSocket  
tags: WebSocket  

---

```
GET /chat HTTP/1.1
Host: server.example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
Origin: http://example.com
```

```
Upgrade和Connection告诉服务器，C端发起的是WebSocket协议
Sec-WebSocket-Key客户端随机生成数字，并将该数字进行Base64编码
Sec_WebSocket-Protocol用户定义的字符串，区分同URL下，不同服务所需的协议；
```

```
: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
```
