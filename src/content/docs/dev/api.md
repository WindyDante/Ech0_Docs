---
title: API文档
description: API接口文档和使用指南
---

## User功能API 

**基础URL**: `http://ip:6277/api`

### 登录
```
POST /login
```

**描述**: 用户登录接口

**请求体**:
```json
{
  "username": "1",
  "password": "1"
}
```

**响应示例**:
```json
{
  "code": 1,
  "msg": "登陆成功",
  "data": "会返回一段token"
}
```




### 注册
```
POST /register
```

**描述**: 用户注册接口

**请求体**:
```json
{
  "username": "1",
  "password": "1"
}
```

**响应示例**:
```json
{
  "code": 1,
  "msg": "注册成功",
  "data": null
}
```



### 获取所有用户
```
GET /allusers
```

**描述**: 获取所有用户及其基本信息接口

**响应示例**:
```json
{
  "code": 1,
  "msg": "获取用户列表成功",
  "data": [
    {
      "id": 2,
      "username": "2",
      "password": "",
      "is_admin": false,
      "avatar": ""
    }
  ]
}
```


### 获取用户信息
```
GET /user
```

**描述**: 获取当前登录用户的信息

**请求头**:
```
Authorization: Bearer <your_token>
```

**响应示例**:
```json
{
  "code": 1,
  "msg": "获取用户信息成功",
  "data": {
    "id": 1,
    "username": "1",
    "password": "",
    "is_admin": true,
    "avatar": ""
  }
}
```

### 更新用户信息
```
PUT /user
```

**描述**: 更新当前登录用户的信息

**请求头**:
```
Authorization: Bearer <your_token>
```

**请求体**:
```json
{
  "username": "1",
  "password": "",
  "is_admin": true,
  "avatar": "/images/Kimomimi_1_2_🌧.webp_ede2a332-17ab-4c01-9422-c260c26d3ac5.png"
}
```

**响应示例**:
```json
{
  "code": 1,
  "msg": "更新用户信息成功",
  "data": null
}
```

### 删除用户
```
DELETE /user/用户id
```

**描述**: 删除指定用户

**请求头**:
```
Authorization: Bearer <your_token>
```

**权限要求**: 
- 需要管理员或系统管理员权限
- 必须在请求头中携带有效的管理员token

**路径参数**:
- `用户id` (integer): 要删除的用户ID

**响应示例**:
```json
{
  "code": 1,
  "msg": "删除用户成功",
  "data": null
}
```

### 更新用户权限
```
PUT /user/admin/:id
```

**描述**: 更新指定用户权限

**请求头**:
```
Authorization: Bearer <your_token>
```

**权限要求**: 
- 需要管理员或系统管理员权限
- 必须在请求头中携带有效的管理员token

**路径参数**:
- `用户id` (integer): 要更新权限的用户ID

**响应示例**:
```json
{
  "code": 1,
  "msg": "更新用户信息成功",
  "data": null
}
```

## Echo功能API

## Setting功能API

## Todo功能API

## Connect功能API