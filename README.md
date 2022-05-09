
### 提醒：滥用可能导致账户被删除！！！ 

## 服务端创建操作流程 
0）给本项目个stars

1）将本项目fork至自己仓库修改`Deploy to Heroku`按键指向地址为自己仓库地址

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/a11874430/yovls)  
2）点击上面紫色`Deploy to Heroku`，会跳转到heroku app创建页面，填上应用程序名、选择节点（美国或者欧洲），点击下面deploy，几秒后搞定！   



## vmess vless 对应客户端参数的参考如下,末尾带()里的内容仅为提示

## 1：Vmess&Vless

### 代理协议：vless+ws+tls 或 vmess+ws+tls
* 服务器地址：cloudflare反代域名
* 端口：443
* 默认UUID：8f91b6a0-e8ee-11ea-adc1-0242ac120002 
* 加密：none
* 传输协议：ws
* 伪装类型：none
* vmess path路径：/8f91b6a0-e8ee-11ea-adc1-0242ac120002-vmess    (注意：前有斜杠/)
* vless path路径：/8f91b6a0-e8ee-11ea-adc1-0242ac120002-vless 
* vmess额外id（alterid）：0
* 底层传输安全：tls
* 跳过证书验证：false

##cloudflare反代代码

```
addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="HEROKU域名.herokuapp.com";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)
```

