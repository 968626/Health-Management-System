# 🏥 荣成市健康管理系统
# 源码获取：https://mbd.pub/o/bread/YZWcmJtsZw==

<p align="center">
  <img src="https://img.shields.io/badge/Spring%20Boot-2.5.2-green.svg" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Vue-3.2.4-blue.svg" alt="Vue">
  <img src="https://img.shields.io/badge/MySQL-8.0-orange.svg" alt="MySQL">
  <img src="https://img.shields.io/badge/Java-1.8-red.svg" alt="Java">
  <img src="https://img.shields.io/badge/Element--Plus-2.3.7-blue.svg" alt="Element Plus">
</p>

<p align="center">
  基于 Spring Boot + Vue3 的全栈健康管理系统，提供体检预约、健康资讯、报告查询等功能。
</p>

## 📋 项目介绍

荣成市健康管理系统是一个面向市民的健康管理平台，旨在提供便捷的体检预约服务、健康资讯浏览、体检报告查询等功能。系统采用前后端分离架构，后端使用 Spring Boot 框架，前端使用 Vue3 + Element Plus 技术栈。

### ✨ 核心功能

- 🔐 **用户管理** - 支持用户注册、登录、权限管理、角色分配
- 📅 **体检预约** - 在线预约体检，支持多种体检套餐选择
- 📊 **体检套餐** - 提供多种预设体检套餐，支持自定义检查组
- 📰 **健康资讯** - 发布和浏览健康相关资讯文章
- 📄 **报告查询** - 在线查看和下载体检报告（支持PDF导出）
- 📈 **数据统计** - 用户分布统计、预约数据分析
- 🗺️ **区域管理** - 支持按区域管理用户和预约信息
- 💬 **消息通知** - 系统消息和预约提醒功能

## 🛠️ 技术栈

### 后端技术

| 技术 | 版本 | 说明 |
|------|------|------|
| Spring Boot | 2.5.2 | 核心框架 |
| Spring Security | - | 安全认证与授权 |
| MyBatis Plus | 3.4.3.1 | ORM 框架 |
| MySQL | 8.0 | 数据库 |
| Druid | 1.2.3 | 数据库连接池 |
| JWT | 3.4.0 | 身份认证 |
| WebSocket | - | 实时通信 |
| 阿里云 OSS | 3.10.2 | 文件存储 |
| Hutool | 5.7.3 | 工具类库 |
| POI | 4.1.2 | Excel 处理 |
| X-EasyPDF | 2.11.2 | PDF 生成 |

### 前端技术

| 技术 | 版本 | 说明 |
|------|------|------|
| Vue | 3.2.4 | 前端框架 |
| Vue Router | 4.0.11 | 路由管理 |
| Vuex | 4.0.0 | 状态管理 |
| Element Plus | 2.3.7 | UI 组件库 |
| Axios | 0.21.1 | HTTP 请求 |
| ECharts | 5.1.2 | 数据可视化 |
| WangEditor | 4.7.6 | 富文本编辑器 |
| Moment.js | 2.29.4 | 日期处理 |

## 📁 项目结构

```
RC-Health-main/
├── healthBoot/                 # 后端项目
│   ├── src/main/java/com/example/health/
│   │   ├── common/            # 公共配置
│   │   ├── controller/        # 控制器层
│   │   ├── entity/            # 实体类
│   │   ├── mapper/            # 数据访问层
│   │   ├── service/           # 业务逻辑层
│   │   ├── utils/             # 工具类
│   │   └── HealthBootApplication.java
│   ├── src/main/resources/
│   │   ├── mapper/            # MyBatis XML
│   │   └── application.yml    # 配置文件
│   └── pom.xml
│
├── healthVue/                  # 前端项目
│   ├── src/
│   │   ├── assets/            # 静态资源
│   │   ├── components/        # 公共组件
│   │   ├── layout/            # 布局组件
│   │   ├── router/            # 路由配置
│   │   ├── store/             # Vuex 状态管理
│   │   ├── utils/             # 工具函数
│   │   ├── views/             # 页面组件
│   │   ├── App.vue
│   │   └── main.js
│   ├── public/
│   └── package.json
│
├── health_system.sql          # 数据库脚本
└── README.md
```

## 🚀 快速开始

### 环境要求

- JDK 1.8+
- MySQL 8.0+
- Node.js 14+
- Maven 3.6+

### 后端部署

1. **创建数据库**
   ```sql
   -- 创建数据库
   CREATE DATABASE health_system CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   
   -- 导入数据
   source health_system.sql
   ```

2. **修改配置**
   
   编辑 `healthBoot/src/main/resources/application.yml`：
   ```yaml
   spring:
     datasource:
       url: jdbc:mysql://localhost:3306/health_system?useUnicode=true&characterEncoding=utf-8&allowMultiQueries=true&useSSL=false&serverTimezone=GMT%2b8
       username: root
       password: your_password
   ```

3. **启动项目**
   ```bash
   cd healthBoot
   mvn spring-boot:run
   ```
   
   或使用 IDE 运行 `HealthBootApplication.java`

### 前端部署

1. **安装依赖**
   ```bash
   cd healthVue
   npm install
   ```

2. **启动开发服务器**
   ```bash
   npm run serve
   ```

3. **构建生产环境**
   ```bash
   npm run build
   ```

## 🔧 配置说明

### 后端配置 (application.yml)

```yaml
server:
  port: 9090  # 服务端口

spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3308/health_system?...
    username: root
    password: root
    type: com.alibaba.druid.pool.DruidDataSource
  
  servlet:
    multipart:
      max-file-size: 100MB  # 文件上传大小限制

mybatis-plus:
  configuration:
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl  # SQL日志
```

### 前端配置

- 开发环境代理配置：`vue.config.js`
- API 请求基地址：`src/utils/request.js`

## 📊 数据库设计

### 核心表结构

| 表名 | 说明 |
|------|------|
| `user` | 用户信息表 |
| `role` | 角色表 |
| `permission` | 权限表 |
| `user_role` | 用户角色关联表 |
| `role_permission` | 角色权限关联表 |
| `appointment` | 预约信息表 |
| `appointment_rule` | 预约规则表 |
| `check_set_meal` | 体检套餐表 |
| `check_group` | 检查组表 |
| `check_items` | 检查项表 |
| `check_items_data` | 检查项数据表 |
| `check_files` | 体检报告文件表 |
| `news` | 健康资讯表 |
| `message` | 消息通知表 |
| `area` | 区域表 |

## 🔒 安全特性

- **JWT 认证** - 基于 Token 的无状态认证机制
- **Spring Security** - 接口权限控制
- **BCrypt 加密** - 用户密码加密存储
- **跨域处理** - 支持 CORS 跨域请求

## 📝 API 文档

### 用户模块

| 接口 | 方法 | 说明 |
|------|------|------|
| `/user/login` | POST | 用户登录 |
| `/user/register` | POST | 用户注册 |
| `/user` | GET | 分页查询用户 |
| `/user/{id}` | GET | 根据ID查询用户 |
| `/user` | POST | 新增用户 |
| `/user` | PUT | 修改用户 |
| `/user/{id}` | DELETE | 删除用户 |
| `/user/export` | GET | 导出Excel |
| `/user/import` | POST | 导入Excel |

### 预约模块

| 接口 | 方法 | 说明 |
|------|------|------|
| `/appointment` | GET | 分页查询预约 |
| `/appointment` | POST | 新增预约 |
| `/appointment/{id}` | DELETE | 取消预约 |

### 体检套餐模块

| 接口 | 方法 | 说明 |
|------|------|------|
| `/checkSetMeal` | GET | 查询套餐列表 |
| `/checkSetMeal/{id}` | GET | 查询套餐详情 |
| `/checkSetMeal` | POST | 新增套餐 |
| `/checkSetMeal` | PUT | 修改套餐 |


