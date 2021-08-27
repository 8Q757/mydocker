该镜像已发布至[Docker Hub](https://hub.docker.com/r/viticis/debian), 可以使用以下命令直接运行:

```bash
$ docker run -it viticis/debian:10.10
```

---

该镜像为基于debian10.10的换源镜像, 使用[中科大开源镜像](http://mirrors.ustc.edu.cn).

原版debian镜像为官方源, `apt-get` 的速度很慢, 基本无法`update`，`install`.

而不安装vim等编辑器, 又不太方便编辑`sources.list`后再`update`.

---

当然, 也可以使用echo等命令修改源, 或者启动容器时候挂载本机的`/etc/apt/sources.list`.
