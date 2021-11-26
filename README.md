# ADhelper
### 钉钉联动AD域
#### 主要功能:
- 1.解锁账号
- 2.重置密码

### 操作说明:
1. 在钉钉开发者后台建立微应用
2. 在钉钉建立相应的流程
3. 调整配置文件,搭建服务器并运行应用
4. 当相应的审批流程通过后,应用会调用对应的函数进行AD账号操作
5. 执行结果通过工作通知发送给用户

### 注意事项:
1. 可以改成从邮箱信息或者通讯录额外字段直接提取AD账号信息
2. 账号需去除域名部分否则powershell执行出错
3. 开发环境:python3.6.8;apache2.4;nginx1.14
4. 调试完毕后请关闭flask调试模式

### 模块说明:
已改用flask框架重写项目
服务器部署为mod_wsgi+Apache/uwsgi+Nginx
adhelper.wsgi:wsgi接口
main.py:主函数,监听钉钉http回调
Conf.py:配置文件,定义相关数值
DingOpreta.py:钉钉基本操作
ADOperate.py:AD域操作
DingCallbackCrypto.py:钉钉http回调函数
dingtalk:钉钉官方api
venv:虚拟环境
uwsgi.ini:uwsgi配置文件

### 如何修改配置文件:
Conf.py文件已定义相关api所需用到的项及其值
根据项目实际的应用信息,服务器信息等
替换其中的赋值

### 钉钉api的用法以及返回值:
请参考钉钉官方文档
https://developers.dingtalk.com/document/app/server-api-overview
