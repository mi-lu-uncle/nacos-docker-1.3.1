# Nacos Docker 1.3.1

本项目是 [Nacos](https://github.com/alibaba/nacos) 在docker的单机模式+mysql8的运行例子.



## 项目目录

* init.d：配置文件
* nacos-logs: 日志
* sql: nacos数据库语句



## 运行环境

* [Docker](https://www.docker.com/)
  

* 打开浏览器

  link：http://127.0.0.1:8848/nacos/

## 快速开始

打开命令窗口执行：

* 前提条件

  ```powershell
  替换docker-compose.yml中关于数据库的参数为自己的参数。并确保数据库中已经新建了对应的表格，如果没有的话，请新建
  ```

* Clone 项目 并且进入项目根目录

  ```powershell
  git clone https://github.com/paderlol/nacos-docker.git
  cd nacos-docker
  ```


* 启动

  ```powershell
  docker-compose up -d
  ```

* 访问控制台

  浏览器访问：http://127.0.0.1:8848/nacos/


## 属性配置列表



| 属性名称                          | 描述                                                         | 选项                              |
| --------------------------------- | ------------------------------------------------------------ | ----------------------------------- |
| MODE                              | 系统启动方式: 集群/单机                                      | cluster/standalone默认 **cluster**  |
| NACOS_SERVERS                     | 集群地址                                   | p1:port1空格ip2:port2 空格ip3:port3 |
| PREFER_HOST_MODE                  | 支持IP还是域名模式                                           | hostname/ip 默认 **ip**             |
| NACOS_SERVER_PORT                 | Nacos 运行端口                                               | 默认 **8848**                       |
| NACOS_SERVER_IP                   | 多网卡模式下可以指定IP                                       |                                     |
| SPRING_DATASOURCE_PLATFORM        | 单机模式下支持MYSQL数据库                        | mysql / 空 默认:空                 |
| MYSQL_SERVICE_HOST                | 数据库  连接地址                                                |                                     |
| MYSQL_SERVICE_PORT                | 数据库端口                                       | 默认 : **3306**                  |
| MYSQL_SERVICE_DB_NAME             | 数据库库名                                     |                                     |
| MYSQL_SERVICE_USER                | 数据库用户名                                  |                                     |
| MYSQL_SERVICE_PASSWORD            | 数据库用户密码                                    |                                     |
| MYSQL_SERVICE_DB_PARAM          | 数据库连接参数                                     | default : **characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true** |
| MYSQL_DATABASE_NUM                | It indicates the number of database                          | 默认 :**1**                    |
| JVM_XMS                           | -Xms                                                         | 默认 :2g                       |
| JVM_XMX                           | -Xmx                                                         | 默认 :2g                       |
| JVM_XMN                           | -Xmn                                                         | 默认 :1g                       |
| JVM_MS                            | -XX:MetaspaceSize                                            | 默认 :128m                     |
| JVM_MMS                           | -XX:MaxMetaspaceSize                                         | 默认 :320m                     |
| NACOS_DEBUG                       | 是否开启远程DEBUG                                 | y/n 默认 :n                      |
| TOMCAT_ACCESSLOG_ENABLED          | server.tomcat.accesslog.enabled                              | 默认 :false                      |
| NACOS_AUTH_SYSTEM_TYPE      |  权限系统类型选择,目前只支持nacos类型       | 默认 :nacos                          |
| NACOS_AUTH_ENABLE      |  是否开启权限系统       | 默认 :false                          |
| NACOS_AUTH_TOKEN_EXPIRE_SECONDS      |  token 失效时间        | 默认 :18000                          |
| NACOS_AUTH_TOKEN      |  token       | 默认 :SecretKey012345678901234567890123456789012345678901234567890123456789                          |
| NACOS_AUTH_CACHE_ENABLE      |  权限缓存开关 ,开启后权限缓存的更新默认有15秒的延迟      | 默认 : false                          |
| MEMBER_LIST | 通过环境变量的方式设置集群地址 | 例子:192.168.16.101:8847?raft_port=8807,192.168.16.101?raft_port=8808,192.168.16.101:8849?raft_port=8809 |
| EMBEDDED_STORAGE | 是否开启集群嵌入式存储模式 | `embedded`  默认 : none |
| NACOS_AUTH_CACHE_ENABLE      |    nacos.core.auth.caching.enabled      |  default : false                          |
| NACOS_AUTH_USER_AGENT_AUTH_WHITE_ENABLE      |    nacos.core.auth.enable.userAgentAuthWhite      |  default : false                          |
| NACOS_AUTH_IDENTITY_KEY      |    nacos.core.auth.server.identity.key      |  default : serverIdentity                          |
| NACOS_AUTH_IDENTITY_VALUE      |    nacos.core.auth.server.identity.value      |  default : security                          |
| NACOS_SECURITY_IGNORE_URLS      |    nacos.security.ignore.urls      |  default : `/,/error,/**/*.css,/**/*.js,/**/*.html,/**/*.map,/**/*.svg,/**/*.png,/**/*.ico,/console-fe/public/**,/v1/auth/**,/v1/console/health/**,/actuator/**,/v1/console/server/**`                          |
