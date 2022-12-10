教程文档：https://ehang-io.github.io/nps/#/?id=nps

## 配置文件说明
- 服务端配置文件(nps.conf)  
![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210155831.png)

- 客户端配置文件(npc.conf)  
![](https://kevin2li-storage.oss-cn-nanjing.aliyuncs.com/20221210155945.png)  

示例配置文件：
```ini
[common]
server_addr=1.1.1.1:8024
conn_type=tcp
vkey=123
username=111
password=222
compress=true
crypt=true
rate_limit=10000
flow_limit=100
remark=test
max_conn=10
#pprof_addr=0.0.0.0:9999
```

## 安装与使用
### 服务端
```bash
cp docker-compose.yaml.nps docker-compose.yaml
# 修改conf/nps.conf(主要修改web_username, web_password, web_ip, bridge_port这几项)
docker compose up -d
```

### 客户端
```bash
cp docker-compose.yaml.npc docker-compose.yaml
# 修改conf/npc.conf
docker compose up -d
```
