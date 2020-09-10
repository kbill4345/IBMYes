# [星际云网络加速-注册即送50G免费流量](https://www.xjycloud.xyz)
# [星云网络加速](https://www.xjycloud.pw)

# IBMYes
请合理使用本公用VPS，建议仅作为备用节点若追求4K或高清的人建议合理避让远离，或其他开发之用例如telegram-bot\python等的开发！

# 注意：本项目Fork自CCChieh大神——【在此感谢大神】因链接子项目被删除故备份此处重新添加子项目
项目安装包括3部分
1. IBM Cloud Fonudray搭建V2Ray ws
2. 利用Github的Actions 每周重启 IBM Cloud Fonudray
3. Cloudflare 高速节点中转

```shell
wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/siemenstutorials/IBMYes/master/install.sh && chmod +x install.sh  && ./install.sh
````
# 利用Github的Actions 每周重启 IBM Cloud Fonudray

IBM Cloud 10天不操作就会关机，所以我们需要 十天内对其重启一次，避免关机。

首先登录IBM Cloud

点击又上角的命令行

在这一步我们主要是记录4个值

 ```
IBM_ACCOUNT // IBM Cloud的登录邮箱和密码
IBM_APP_NAME // 应用的名称
REGION_NUM // 区域编码
RESOURSE_ID // 资源组ID
 ```

```shell
ibmcloud login
```
输入邮箱和密码。

```
#1. au-syd
#2. in-che
#3. jp-tok
#4. kr-seo
#5. eu-de
#6. eu-gb
#7. us-south
#8. us-east
```
这里需要记下和区域对应的编号也就是`REGION_NUM`，比如我这里是us-south,那么我的区域编号是`7`

接下来获取资源组id`RESOURSE_ID`
```shell
ibmcloud resource groups
```
New secret
分别建立四个secret

```
IBM_ACCOUNT // IBM Cloud的登录邮箱和密码
IBM_APP_NAME // 应用的名称
REGION_NUM // 区域编码
RESOURSE_ID // 资源组ID
```

第一行为邮箱，第二行为密码。

打开和复制脚本

```
addEventListener(
"fetch",event => {
let url=new URL(event.request.url);
url.hostname="ibmyes.us-south.cf.appdomain.cloud";
let request=new Request(url,event.request);
event. respondWith(
fetch(request)
)
}
)
```

# 免责申明
本项目Fork源自CCChieh/IBMYes，在此仅作备份
