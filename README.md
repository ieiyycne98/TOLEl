# okteto部署vless

### okteto地址：https://okteto.com/

### 变量

对部署时需设定的变量名称做如下说明：

服务器地址：Endpoint

端口：443

AID：0

UUID: f41d13f5-82f0-4807-b018-481643f9826c

路径：/tixiaohanhidden

### 通过 CloudFlare Workers 反向代理

```js
addEventListener(
    "fetch",event => {
    let url=new URL(event.request.url);
    url.hostname="xxx.cloud.okteto.net;
    let request=new Request(url,event.request);
    event. respondWith(
      fetch(request)
    )
  }
)
```

