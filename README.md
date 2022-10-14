# MyDocker
该项目用以备份和分享一些常用且好用的Docker项目。

---



## Overview

1. 该仓库中容器均基于同一个自定义网络，这样做的好处是与宿主机网络隔离，并且内网互通，还可以使用主机名即容器的名字直接访问。例如，使用Nginx映射某个Web服务，不需要使用可能会变动的IP地址，而是使用Web服务的容器名字+端口号的形式即可，而Web服务的容器需要依赖于数据库时，也只需要使用数据库的容器名字进行连接。您可以将`dev`换成任何您喜欢的名字，但请记得将`docker-compose.yml`同步更换为一样的名字，使用以下命令新建网络：

```shell
docker network create dev
```

2. 该项目中所有容器的数据，配置文件等需要持久化保存的内容，均通过`volumes`映射至`docker-compose.yml`所在目录，如需迁移或备份服务，直接将`docker-compose.yml`所在目录整体拷贝即可，重新启动不会丢失数据。
3. 部分容器依赖于MySQL数据库，此处选择MariaDB，为节省内存，将MariaDB单独作为一个容器，供其他容器使用。

---



## Project

| 项目                                                          | 备注                                                                                            | 目录                                                                                       |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| [MariaDB](https://mariadb.org/)                               | 数据库，默认密码为`root`。                                                                      | [mariadb](https://github.com/viticis/mydocker/tree/master/mariadb)                         |
| [Nginx Proxy Manager](https://nginxproxymanager.com/)         | 可视化的Nginx管理面板，在浏览器中添加反向代理，申请SSL证书等。                                  | [nginx-proxy-manager](https://github.com/viticis/mydocker/tree/master/nginx-proxy-manager) |
| [Next Terminal](https://next-terminal.typesafe.cn/)           | 一个轻量级堡垒机系统，易安装，易使用，支持RDP、SSH、VNC、Telnet、Kubernetes协议。               | [next-terminal](https://github.com/viticis/mydocker/tree/master/next-terminal)             |
| [UptimeRobot Page](https://github.com/giuem/uptimerobot-page) | 基于[Uptime Robot](https://uptimerobot.com/)的展示页面。                                        | [uptime](https://github.com/viticis/mydocker/tree/master/uptime)                           |
| [为知笔记](https://www.wiz.cn/zh-cn/docker)                   | 为知笔记破解版，无限用户。                                                                      | [wiz](https://github.com/viticis/mydocker/tree/master/wiz)                                 |
| [vaultwarden](https://github.com/dani-garcia/vaultwarden)     | [Bitwarden](https://bitwarden.com/)的第三方服务端，使用Rust实现。                               | [vaultwarden](https://github.com/viticis/mydocker/tree/master/vaultwarden)                 |
| [Drone](https://www.drone.io/)                                | 轻量级的持续集成。                                                                              | [drone](https://github.com/viticis/mydocker/tree/master/drone)                             |
| [acme.sh](https://github.com/acmesh-official/acme.sh)         | 纯 shell 命令的acme 协议实现，可以从 [Let's encrypt](https://letsencrypt.org/) 生成免费的证书。 | [drone](https://github.com/viticis/mydocker/tree/master/acme.sh)                           |
| [Focalboard](https://www.focalboard.com/)                     | Focalboard 是 Asana、Trello 和 Notion 等工具的开源替代品。                                      | [focalboard](https://github.com/viticis/mydocker/tree/master/focalboard)



---

