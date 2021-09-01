
## Grafana + Prometheus + node-exporter + cAdvisor

> 运维数据采集, 监控, 展示, 报警方案

```bash
$ mkdir -p /etc/prometheus && cd /etc/prometheus
$ curl -O https://github.com/viticis/mydocker/blob/master/grafana_prometheus_node-exporter_cadvisor/prometheus/prometheus.yml
$ mkdir -p /etc/grafana && cd /etc/grafana
$ curl -O https://github.com/viticis/mydocker/blob/master/grafana_prometheus_node-exporter_cadvisor/grafana/grafana.ini
```

---

使用上述命令下载好配置文件, 在`docker-compose.yml`同级目录中输入`docker-compose up -d`启动容器.

访问`http://ip:3000/`, 默认账户为`admin`, 默认密码为`admin`.

添加Data sources, 选择Prometheus, URL为`prometheus:9090`.

Import新的dashboard, 输入ID, 例如`13112`.

---
1. 上述命令均需要sudo权限
2. 该仓库`grafana.ini`配置文件中, 已经打开了匿名访问, 可自行修改
3. 部分情况挂载的该配置文件不生效, 原因是grafana使用了容器内的默认配置文件`/usr/share/grafana/conf/defaults.ini`
