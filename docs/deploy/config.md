# 配置文件说明

## 前端

位于 `usr/config.json`

| Key | Value | Description | Example |
| :---: | :---: | --- | --- |
| api.backend | URL | Backend's address | `"/api/"` |
| api.admin | URL | Admin's address | `""` |
| footer | JSON Array | Custom frontend footer's link | `[]` |
| footer.url | URL | Link's URL | `"http://blog.lucien.ink/go/csdn"` |
| footer.text | Text | Link's text | `"CSDN"` |

### 示例

`config.example.json`

```json
{
  "api": {
    "backend": "/_api/backend/",
    "admin": ""
  },
  "footer": [
    {
      "url": "http://blog.lucien.ink/go/csdn",
      "text": "CSDN"
    },
    {
      "url": "https://github.com/LucienShui",
      "text": "GitHub"
    }
  ]
}
```

## 后端

| Key | Description | Example |
| :---: | --- | --- |
| `version` | Config file's version, **DON'T** change this field yourself | `"3.3.0"` |
| `address` | Listen address | `"0.0.0.0"` |
| `admin_address` | Admin's address, `""` for disable admin | `""` |
| `port` | Listen port | `8000` |
| `database.type` | Data Source, `mysql` for using MySQL, another for using SQLite3 | `"mysql"` |
| `database.username` | Database username | `"username"` |
| `database.password` | Database password | `"password"` |
| `database.server` | MySQL server address | `"localhost"` |
| `database.port` | MySQL server port | `3306` |
| `database.database` | Database name | `"pasteme"` |

### 示例

`config.example.json`

```json
{
  "version": "3.3.0",
  "address": "0.0.0.0",
  "admin_url": "",
  "port": 8000,
  "database": {
    "type": "mysql",
    "username": "username",
    "password": "password",
    "server": "pasteme-mysql",
    "port": 3306,
    "database": "pasteme"
  }
}
```
