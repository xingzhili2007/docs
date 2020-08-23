# 前端部署指南

## 下载并解压

从 [release](https://github.com/PasteUs/PasteMeFrontend/releases/latest) 下载 `pasteme.tar.gz` 并解压

## 编辑配置文件

新建文件 `usr/config.json`，详情见 [前端配置文件说明](config.md#前端)

## 将所有请求重定向至 index.html

### Nginx

```
location / {
    try_files $uri $uri/ /index.html;
}
```
