## 用户登录系统接口文档

### 1. 用户注册接口

**接口URL:** POST /users/signup

**请求参数:**

| 参数名          | 类型   | 必填 | 描述     |
| --------------- | ------ | ---- | -------- |
| email           | string | 是   | 用户邮箱 |
| password        | string | 是   | 用户密码 |
| confirmPassword | string | 是   | 确认密码 |

**请求示例:**

```json
{
  "email": "user@example.com",
  "password": "Password123!",
  "confirmPassword": "Password123!"
}
```

**响应结构:**

- 成功时响应:

```json
{
  "message": "注册成功"
}
```

- 失败时响应:

```json
{
  "error": "错误信息"
}
```

### 2. 用户登录接口

**接口URL:** POST /users/login

**请求参数:**

| 参数名   | 类型   | 必填 | 描述     |
| -------- | ------ | ---- | -------- |
| email    | string | 是   | 用户邮箱 |
| password | string | 是   | 用户密码 |

**请求示例:**

```json
{
  "email": "user@example.com",
  "password": "Password123!"
}
```

**响应结构:**

- 成功时响应:

```json
{
  "message": "登录成功"
}
```

- 失败时响应:

```json
{
  "error": "错误信息"
}
```

### 3. 用户编辑个人信息接口

**接口URL:** POST /users/edit

**请求参数:**

| 参数名          | 类型   | 必填 | 描述       |
| --------------- | ------ | ---- | ---------- |
| newPassword     | string | 否   | 新密码     |
| confirmPassword | string | 否   | 确认新密码 |

**请求示例:**

```json
{
  "newPassword": "NewPassword456!",
  "confirmPassword": "NewPassword456!"
}
```

**响应结构:**

- 成功时响应:

```json
{
  "message": "个人信息已更新"
}
```

- 失败时响应:

```json
{
  "error": "错误信息"
}
```

### 4. 查看个人详情接口

**接口URL:** GET /users/profile

**响应结构:**

- 成功时响应:

```json
{
  "email": "user@example.com"
}
```

- 失败时响应:

```json
{
  "error": "错误信息"
}
```

### 5. JWT登录和用户详情接口

**接口URL:** POST /users/login（JWT版本）、GET /users/profile（JWT版本）

**请求参数:**

| 参数名   | 类型   | 必填 | 描述     |
| -------- | ------ | ---- | -------- |
| email    | string | 是   | 用户邮箱 |
| password | string | 是   | 用户密码 |

**请求示例:**

```json
{
  "email": "user@example.com",
  "password": "Password123!"
}
```

**响应结构:**

- 成功时响应:

```json
{
  "message": "登录成功",
  "token": "JWT令牌"
}
```

- 失败时响应:

```json
{
  "error": "错误信息"
}
```