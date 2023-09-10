# Nginx配置
## 启动Nginx容器
```
docker run -d -p 80:80 --name my-nginx-container \
  -v /home/ooodjc/docker/nginx/conf:/etc/nginx/conf.d \
  -v /home/ooodjc/docker/nginx/html:/usr/share/nginx/html \
  --restart always nginx
```