# 后端部署指南

## 下载并解压

从 [release](https://github.com/PasteUs/PasteMeGoBackend/releases/latest) 下载 `pastemed-linux-amd64.tar.gz` 并解压

## 编辑配置文件

新建文件 `config.json`，详情见 [后端配置文件说明](config.md#后端) `config.json`

## 启动 pastemed

```bash
./pastemed -c ./config.json -d ./
```

### pastemed 的启动参数

```bash
Usage of pastemed:
  -c string
        -c <config file> (default "./config.json")
  -d string
        -d <data dir> (default "./")
  -debug
        --debug Using debug mode
  -version
        --version Print version information
```
