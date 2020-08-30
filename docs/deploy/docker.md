# 使用 Docker 部署 PasteMe

若要使用 Nginx 和 systemd 部署请移步：[朴素部署](deploy/directly/)

## 部署

1. 克隆 [github.com/PasteUs/PasteMeDeploy](https://github.com/PasteUs/PasteMeDeploy)，并进入克隆至本地的文件夹

    ```bash
    git clone https://github.com/PasteUs/PasteMeDeploy --depth=1 pasteme
    cd pasteme
    ```

2. 启动服务

    ```bash
    docker-compose up -d
    ```

命令执行完成后等待 `30s`（因为需要初始化数据库和等待 `healthy check`），然后运行 `docker ps -a`，当看到所有的容器的状态没有 `unhealthy` 或 `Exited (x) xxx` 就代表 PasteMe 已经启动成功

## 更新

1. 进入到克隆至本地的文件夹

    ```bash
    cd pasteme
    ```

2. 更新项目

    ```bash
    git pull
    ```

3. 更新容器

    ```bash
    docker-compose pull
    docker-compose up -d
    ```

## 查看日志

+ 前端 `Nginx` 日志位于 `frontend/logs` 下
+ 后端日志通过 `docker logs pasteme-backend` 查看
+ 数据库日志通过 `docker logs pasteme-mysql` 查看

## 鸣谢

[OnlineJudgeDeploy](https://github.com/QingdaoU/OnlineJudgeDeploy)
