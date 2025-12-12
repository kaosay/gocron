# gocron
How to use and install gocron

```
# docker-compose.yml   （直接保存运行就行）
version: '3.8'

services:
  gocron:
    image: ouqg/gocron
    container_name: gocron
    restart: unless-stopped
    ports:
      - "5920:5920"                 # Web 界面端口
    volumes:
      - ./gocron-data:/gocron/data   # 持久化任务和日志（重要！）
        #- /var/run/docker.sock:/var/run/docker.sock  # 可选：支持执行 Docker 命令
    environment:
      - TZ=Asia/Shanghai
      - GOCRON_ENV=production
    # 如果你想改默认账号密码（默认 admin/123456）
    #   - GOCRON_ADMIN_USER=admin
    #   - GOCRON_ADMIN_PASS=your-strong-password
```
