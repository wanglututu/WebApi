# 微信mac/ipad协议，webapi本地部署
首次可以免费试用1天，想要继续租用或购买请联系qq：929918989

1.新机器首次需要进入cmd，关闭windows数据保护DEP（dep可能会导致不安全代码闪退）：bcdedit.exe/set {current} nx AlwaysOff，重启电脑<br/><br/>
2.下载项目，进入mac/ipad目录，打开WeChatServer.exe.config<br/><br/>
3.配置api端口，和websocket端口，管理员密码等参数
```  
    <add key="WebApiHost" value="22221" />
    <add key="WebSocketHost" value="22222" />
    <add key="AdminPassword" value="123456" />
```
4.右键管理员运行WeChatServer.exe，看见  开启服务... 证明服务已经开启<br/><br/>
5.在浏览器运行http://localhost:22221/swagger/ 即可查看所有webapi文档<br/><br/>
6.请先仔细阅读Test.html代码，通过websocket创建连接，获取二维码登录后才可调用api。详细信息可以查看浏览器控制台Console和Network<br/><br/>
7.微信登录获取二维码需要参考Test.html中websocket方式创建websocket链接来获取二维码登录。uuid为创建websocket时传入参数<br/><br/>
8.在微信成功登录以后，即可通过Http post的方式传入uuid来操作微信了<br/><br/>