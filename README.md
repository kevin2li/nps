教程文档：https://ehang-io.github.io/nps/#/?id=nps
# 安装
nps支持多种安装方式，包括源码安装、二进制安装、docker安装。本教程只介绍docker版的安装方法，其他安装方法可自行查看文档。

## 服务端
```bash
git clone https://github.com/kevin2li/nps.git
cd nps
cp docker-compose.yaml.nps docker-compose.yaml
# 编辑conf/nps.conf
docker compose up -d
```
`conf/nps.conf`主要修改以下字段：
- `bridge_port`：nps服务端与npc客户端通信的端口，该端口需要在服务器防火墙放行
- `web_username`: nps网页端账号名称
- `web_password`: nps网页端账号密码
- `web_port`: nps网页端口

其他字段可以根据需要自行修改。

## 客户端
```bash
git clone https://github.com/kevin2li/nps.git
cd nps
cp docker-compose.yaml.npc docker-compose.yaml
# 编辑conf/npc.conf
docker compose up -d
```
`conf/npc.conf`主要修改以下字段：
- `server_addr`：nps云服务器ip及bridge_port端口，例如: 1.1.1.1:8024
- `vkey`: nps网页上添加客户端时生成的vkey(唯一验证密钥)

其他字段可以根据需要自行修改。

# 使用
## 创建客户端
1. 点击“添加”，添加一个客户端 
 
![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210193837.png)

2. 填写客户端信息  

![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210194005.png)

4. 在客户端列表页面，记录vkey信息(唯一验证密钥)，并填入客户端配置文件`conf/npc.conf`的vkey字段

6. 客户端编辑好npc.conf后启动，网页端显示客户端在线表示连接成功。

## 创建隧道
以创建TCP隧道为例：  
1. 在侧边栏"TCP隧道"板块，点击"添加"

![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210195939.png)

2. 填写隧道基本信息后，点击"保存"后，隧道即创建成功

![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210200200.png)