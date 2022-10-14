该服务需要 websocket 支持，以 nginx 配置为例：

```
server {
    # Omit...

    location ~ /ws/* {
       proxy_set_header Upgrade $http_upgrade;
       proxy_set_header Connection "upgrade";
       client_max_body_size 50M;
       proxy_pass http://focalboard:8000;
   }

   location / {
       client_max_body_size 50M;
       proxy_pass http://focalboard:8000;
   }

}
```
更多信息可以参阅[官方仓库](https://github.com/mattermost/focalboard/tree/main/docker)。
