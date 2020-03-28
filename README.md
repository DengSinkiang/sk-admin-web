# SKADMIN-WEB

SKADMIN 前端源码

#### 项目源码

|     |   后端源码  |   前端源码  |
|---  |--- | --- |
|  github   |  https://github.com/DengSinkiang/skadmin   |  https://github.com/DengSinkiang/skadmin-web   |

#### 前端模板

初始模板基于： [https://github.com/PanJiaChen/vue-element-admin](https://github.com/PanJiaChen/vue-element-admin)

模板文档： [https://panjiachen.github.io/vue-element-admin-site/zh/guide/](https://panjiachen.github.io/vue-element-admin-site/zh/guide/)

#### Build Setup
``` bash
# 安装依赖
npm install

# 启动服务 localhost:8013
npm run dev

# 构建生产环境
npm run build
```

### nginx 没有安装nginx请自行百度安装
```
server {
    listen       80;
    server_name  前端页面 # www.rbac.com;

    proxy_set_header X-Forwarded-Host $host;
    proxy_set_header X-Forwarded-Server $host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    location / {
        proxy_pass http://127.0.0.1:8013;
        proxy_connect_timeout 600;
        proxy_read_timeout 600;
    }

}
server {
    listen       80;
    server_name  api页面 # api.rbac.com;

    proxy_set_header X-Forwarded-Host $host;
    proxy_set_header X-Forwarded-Server $host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_connect_timeout 600;
        proxy_read_timeout 600;
    }

}
# 修改 prod.env.js
BASE_API: '"api地址 # http://api.rbac.com"'
```

