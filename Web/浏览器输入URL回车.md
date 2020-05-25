# 浏览器输入URL回车

## DNS解析

- 本机Host
- DNS查询
  - 浏览器缓存
  - 本机缓存
  - 路由器/网关缓存
  - ISP DNS服务器
  - DNS根服务器
  - 递归查询
  - 迭代查询

## 建立http/https连接
- TCP连接
  - 三次握手
  - 四次挥手
- HTTP
  - 建立在TCP协议上的应用
  - 明文
- HTTPS
  - RSA等非对称加密交换密钥
  - 使用DES等对称加密加密数据
  - 非对称加密速度慢，只能加密比密钥短的内容 

## 请求
- Request Header
  - Method URL `POST / HTTP/1.1` 
  - Host
  - Connection `keep alive`
  - Content-Length
  - Accept `*/*`
  - Origin
  - Referer
  - Cookie
  - User-Agent
  - Pragma
  - Cache-Control
  - If-Modified-Since
  - If-None-Match
- Request Body

## 服务器处理
- host:port 确定主机和服务端口
- webserver 处理请求，通过URL规则分别处理静态资源和动态请求
- 动态请求通过fastcgi转发处理并返回

## 响应
- Response Header
  - State protocal/status `HTTP/1.1 200 OK`
    - 1xx 消息
    - 2xx 成功
    - 3xx 重定向 `301` `302` `304`
    - 4xx 请求错误 `400` `403`
    - 5xx 服务器错误 `500` `502` `504`
  - Content Type `text/html`
  - Content-Encoding `gzip`
  - Content-Length
  - Cache-Control
  - Last-Modified 
  - Expires
  - Etag
- Response Body

## 浏览器缓存
- 仅针对URL完全相同的GET请求
- 强制缓存 浏览器直接使用本地资源，不向服务器发送任何请求，`from memory/disk cache`
- 协商缓存 浏览器通过`If-Modified-Since/If-None-Match`等字段向服务器询问资源是否过期，若服务端返回`304`则可使用原有缓存
- Pragma
  - `no-cache`
- Cache-Control 请求头中使用表示控制此次请求的缓存策略，响应头中使用表示指导客户端的缓存策略
  - `max-age` 告知客户端资源在时间内有效，可走强制缓存
  - `no-cache` 不使用缓存，即使原来有缓存也不使用
  - `no-store` 不进行缓存存储，也就无法使用缓存
  - `public` 允许包括代理服务器在内的所有地方缓存内容
  - `private` 默认值，只允许客户端缓存内容

## CDN
- 通过CDN服务器提供静态资源，减小源服务器压力，加快资源获取速度

## 渲染
- HTML从上至下逐行解析
- 构建DOM树
- 构建CSS树
- 合并DOM和CSS，渲染树
- 递归渲染
- JS执行
