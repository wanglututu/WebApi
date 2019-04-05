# 微信mac/ipad协议，webapi免IIS部署版本。
 请进入  http://www.wechattools.com/ 进行注册授权<br/><br/>
1.找到mac/ipad目录<br/><br/>
2.打开WeChatServer.exe.config<br/><br/>
3.配置授权信息，api端口，和websocket端口，接收消息回调接口地址，管理员密码等参数<br/><br/>
```  
    <add key="AuthKey" value="" />
    <add key="WebApiHost" value="22221" />
    <add key="WebSocketHost" value="22222" />
    <add key="MsgCallBackUrl" value="" />
    <add key="AdminPassword" value="123456" />
```
<br/><br/>
4.右键管理员运行 WeChatServer.exe
看见  开启服务... 证明服务已经开启<br/><br/>
5.在浏览器运行http://localhost:22221/swagger/ 即可查看所有webapi文档。（请先仔细阅读test.html 代码 通过websocket创建连接 获取二维码登录后才可调用api）<br/><br/>
6.微信登录获取二维码需要参考Test.html 中websocket方式创建websocket链接来获取二维码登录。uuid为创建websocket时传入参数。<br/><br/>
7.提供两种登录方式 ：1、二维码登录  2、账号密码+62登录  （通过二维码登录以后 调用api获取到62数据 保存下来后即可通过账号密码+62进行登录）<br/><br/>
8.在微信成功登录以后，即可通过Http post的方式传入uuid来操作微信了<br/><br/>
9.请<a target="_blank" href="https://jingyan.baidu.com/article/335530daab956419cb41c38a.html">关闭dep</a> ，dep可能会导致不安全代码闪退。<br/><br/>
10.消息回调通过websocket 异步回调的方式返回，如果websocket不在线则无法接受到消息回调，如果有特殊需求可以联系群主索要代码自行修改消息回调逻辑，例如存入数据库或对其他应用api进行调用。<br/><br/>

demo源码暂时不放github了。如需要研究源码学习，请加入我的知识星球。<br/>
demo源码使用c#进行开发，开发环境为VS2017 .net framework 4.6.1<br/>
![](https://github.com/changtuiqie/WeChatAgreement.WebApi.Simple/blob/master/zsxq.jpg) <br/>