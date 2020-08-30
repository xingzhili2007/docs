# 朴素部署 PasteMe

`2.x` 与 `3.x` 的数据库表结构并不相同，需要进行数据迁移，详见：[数据迁移](migrate.md)

朴素部署部分仅推荐对 Linux 比较了解的小伙伴的小伙伴进行尝试，不保证文档的绝对正确性

**推荐使用 docker 以避免诸多问题**

> Docker 部署请移步：[使用 docker 部署 PasteMe](deploy_docker.md)

## 结构

![](PasteMe-Architecture.svg)

## 文件树

### 前端

```plain
pasteme
├── conf.d
│   └── nginx.conf # Nginx 配置文件
├── css
│   ├── app.xxx.css.gz
│   ├── chunk-vendors.xxx.css.gz
│   └── not_found.xxx.css.gz
├── favicon.ico
├── img
│   └── donate.xxx.png
├── index.html
├── js
│   ├── app.xxx.js.gz
│   ├── chunk-vendors.xxx.js.gz
│   ├── lang-en.xxx.js.gz
│   └── not_found.xxx.js.gz
├── LICENSE
├── README.md
└── usr
    ├── config.json # 前端配置文件
    └── usr.js # 前端自定义 js
```

### 后端

```plain
pastemed
├── config.json # 后端配置文件
├── pastemed
└── systemd
    └── pastemed.service
```

## 配置文件
+ 前端的配置文件：`usr/config.json`
+ 前端自定义 js：`usr/usr.js`
+ 后端的配置文件：`config.json`
+ Nginx 的配置文件：`conf.d/nginx.conf`

### `nginx.conf`

此配置文件为 `Nginx` 的配置文件，一般来说只需要更改 `server_name` 字段
