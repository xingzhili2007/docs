# API 文档

## Get

### Request

`GET` `api.pasteme.cn/:token` or `api.pasteme.cn/:token?json=true`

> `GET` without `json=true` will only get content field instead.

+ `token` is `100` with Paste ID **100**
+ `token` is `101,123456` with Paste ID **101** and Password **123456**

#### Params

| Name | Type | Description |
| :---: | :---: | --- |
| token | string | \<Paste key\>[,Password] |

### Response 

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description |
| :---: | :---: | --- |
| status | int | request status code |
| lang | string | Paste content's language |
| content | text | Paste content |

##### Example

```json
{
  "status": 200,
  "lang": "bash",
  "content": "echo Hello"
}
```

## Create

### Request

| Method | URL | Description |
| :---: | --- | --- |
| `POST` | `api.pasteme.cn` | Create a permanent paste |
| `POST` | `api.pasteme.cn/once` | Create a temporary paste with random key |

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description | Required |
| :---: | :---: | --- | :---: |
| lang | string | Paste content's language | Yes |
| content | text | Paste's content | Yes |
| password | string | Paste's password | No |

##### Example

```json
{
  "lang": "bash",
  "content": "echo Hello"
}
```

or

```json
{
  "lang": "bash",
  "content": "echo Hello",
  "password": "password"
}
```

### Response 

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description |
| :---: | :---: | --- |
| status | string | Request status code |
| key | string | Paste's key |

##### Example

```json
{
  "status": 201,
  "key": "100"
}
```

## Custom temporary key

### Request

`PUT` `api.pasteme.cn/:key`

#### Params

| Name | Type | Description |
| :---: | :---: | --- |
| key | string | Paste key |

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description | Required |
| :---: | :---: | --- | :---: |
| lang | string | Paste content's language | Yes |
| content | text | Paste's content | Yes |
| password | string | Paste's password | No |

##### Example

```json
{
  "lang": "bash",
  "content": "echo Hello"
}
```

or

```json
{
  "lang": "bash",
  "content": "echo Hello",
  "password": "password"
}
```

### Response 

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description |
| :---: | :---: | --- |
| status | string | Request status code |
| key | string | Paste's key |

##### Example

```json
{
  "status": 201,
  "key": "100"
}
```

## Error

### Response 

#### Headers

`Content-Type: application/json`

#### Body

##### Params

| Name | Type | Description |
| :---: | :---: | --- |
| status | int | Request status code |
| error | string | Error content |
| message | string | Error's detail |

##### Example

```json
{
  "status": 401,
  "error": "unauthorized",
  "message": "wrong password"
}
```