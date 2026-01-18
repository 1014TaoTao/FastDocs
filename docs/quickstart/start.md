---
outline: "deep"
title: 快速开始
---
# 快速开始

## 🍪演示环境

- 官网地址：<https://service.fastapiadmin.com>
- 演示地址：<https://service.fastapiadmin.com/web>
- 小程序地址：<https://service.fastapiadmin.com/app>
- 管理员账号：`admin` 密码：`123456`
- 演示账号：`demo` 密码：`123456`

## 👷安装和使用

### 版本说明

| 类型     | 技术栈     | 版本       |
|----------|------------|------------|
| 后端     | Python         | >=3.10       |
| 后端     | FastAPI        | 0.109      |
| 前端     | Node.js        | >= 20.0（推荐使用最新版）|
| 前端     | npm            | 16.14      |
| 前端     | Vue3           | 3.3        |
| Web UI  | ElementPlus     | 2.10.4        |
| 移动端  | Uni App         | 3.0.0       |
| App UI  | Wot Design Uni  | 1.9.1        |
| 数据库   | MySQL           | 8.0 （推荐使用最新版）|
| 中间件   | Redis           | 7.0 （推荐使用最新版）|

### 环境准备

#### 1. 安装 Python

```sh
# macOS
brew install python@3.10

# Ubuntu/Debian
sudo apt update
sudo apt install python3.10 python3.10-venv python3.10-dev

# CentOS/RHEL
sudo dnf install python3.10 python3.10-venv python3.10-devel
```

#### 2. 安装 Node.js

```sh
# 使用 nvm 安装（推荐）
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install 20
nvm use 20

# 或使用包管理器
# macOS
brew install node@20

# Ubuntu/Debian
sudo apt update
sudo apt install nodejs npm

# CentOS/RHEL
sudo dnf install nodejs npm
```

#### 3. 安装数据库和缓存

```sh
# 安装 MySQL
# macOS
brew install mysql
brew services start mysql

# Ubuntu/Debian
sudo apt update
sudo apt install mysql-server
sudo systemctl start mysql

# 安装 Redis
# macOS
brew install redis
brew services start redis

# Ubuntu/Debian
sudo apt install redis-server
sudo systemctl start redis
```

### 获取代码

```sh
# 克隆代码到本地
# FastapiAdmin 主工程
git clone https://github.com/fastapiadmin/FastapiAdmin.git
# FastApp 移动端
git clone https://github.com/fastapiadmin/FastApp.git
# FastDocs 官网文档
git clone https://github.com/fastapiadmin/FastDocs.git
```

### 本地后端启动（FastapiAdmin 主工程）

#### 1. 配置环境变量

```sh
# 进入后端工程目录
cd FastapiAdmin/backend

# 复制环境配置文件
cp env/.env.dev.example env/.env.dev

# 编辑环境配置文件（根据实际情况修改）
# 主要配置项：数据库连接、Redis连接、JWT密钥等
```

#### 2. 安装依赖

```sh
# 创建虚拟环境（可选但推荐）
python3 -m venv venv

# 激活虚拟环境
# macOS/Linux
source venv/bin/activate
# Windows
venv\Scripts\activate

# 安装依赖
pip install -r requirements.txt
```

#### 3. 数据库初始化

```sh
# 生成迁移文件
python main.py revision "初始化迁移" --env=dev

# 应用迁移
python main.py upgrade --env=dev

# 初始化系统数据
python main.py init
```

#### 4. 启动后端服务

```sh
# 开发环境启动
python main.py run --env=dev

# 或使用默认环境（dev）
python main.py run

# 生产环境启动
python main.py run --env=prod
```

### 本地前端启动（FastapiAdmin 主工程）

#### 1. 配置环境变量

```sh
# 进入前端工程目录
cd FastapiAdmin/frontend

# 复制环境配置文件
cp .env.development.example .env.development

# 编辑环境配置文件（根据实际情况修改）
# 主要配置项：API基础URL等
```

#### 2. 安装依赖

```sh
# 安装 pnpm（如果未安装）
npm install -g pnpm

# 安装前端依赖
pnpm install
```

#### 3. 启动前端服务

```sh
# 开发环境启动
pnpm run dev

# 构建前端, 生成 `dist` 目录
pnpm run build
```

### 本地小程序h5启动（FastApp 移动端）

#### 1. 配置环境变量

```sh
# 进入移动端工程目录
cd FastApp

# 复制环境配置文件
cp .env.development .env.development

# 编辑环境配置文件（根据实际情况修改）
# 主要配置项：API基础URL等
```

#### 2. 安装依赖

```sh
# 安装前端依赖
pnpm install
```

#### 3. 启动H5服务

```sh
# 启动H5开发服务
pnpm run dev:h5

# 构建H5版本, 生成 `dist/build/h5` 目录
pnpm run build:h5

# 启动其他平台（如微信小程序）
pnpm run dev:mp-weixin
```

### 本地项目官网启动（FastDocs 官网文档）

```sh
# 进入 FastDocs 官网文档目录
cd FastDocs

# 安装依赖
pnpm install

# 运行文档工程
pnpm run docs:dev

# 构建文档工程, 生成 `dist` 目录
pnpm run docs:build
```

---

### 本地访问地址

- FastDocs 文档地址: <http://127.0.0.1:5180>
- FastapiAdmin 前端地址: <http://127.0.0.1:5173>
- FastAPI 接口文档: <http://127.0.0.1:8001/api/v1/docs>
- FastApp H5地址: <http://127.0.0.1:5174>

### 默认账号密码

- 管理员账号：`admin` 密码：`123456`
- 演示账号：`demo` 密码：`123456`

## 🐳 Docker 部署

### 1. 准备工作

- 服务器需安装 Docker 和 Docker Compose
- 确保服务器端口 80（Nginx）、8001（后端）可用

### 2. 部署步骤

```sh
# 进入 FastapiAdmin 主工程目录
cd FastapiAdmin

# 复制环境配置文件
cp backend/env/.env.prod.example backend/env/.env.prod
cp frontend/.env.production.example frontend/.env.production

# 编辑环境配置文件（根据实际服务器情况修改）
# 主要配置项：数据库连接、Redis连接、JWT密钥、API基础URL等

# 赋予脚本执行权限
chmod +x start.sh

# 执行部署脚本
./start.sh

# 查看部署状态
docker compose ps

# 查看日志
docker logs -f fastapiadmin-backend
```

### 3. 部署文件说明

| 配置文件 | 说明 | 路径 |
|---------|------|------|
| 后端环境配置 | 生产环境数据库、Redis等配置 | `FastapiAdmin/backend/env/.env.prod` |
| 前端环境配置 | 生产环境API地址等配置 | `FastapiAdmin/frontend/.env.production` |
| Docker配置 | 容器编排配置 | `FastapiAdmin/docker-compose.yaml` |
| Nginx配置 | 反向代理配置 | `FastapiAdmin/devops/nginx/nginx.conf` |

### 4. 常用 Docker 命令

```sh
# 查看镜像
docker images

# 查看容器
docker compose ps

# 停止服务
docker compose down

# 重启服务
docker compose up -d

# 查看容器日志
docker logs -f <容器名>

# 进入容器
docker exec -it <容器名> bash
```

## 🔧模块展示

### web 端

| 模块名 <div style="width:60px"/>  | 截图 |
|----------|------|
| 登录      | ![登录](/login.png) |
| 仪表盘    | ![仪表盘](/dashboard.png) |
| 分析页    | ![分析页](/analysis.png) |
| 菜单管理  | ![菜单管理](/menu.png) |
| 部门管理  | ![部门管理](/dept.png) |
| 岗位管理  | ![岗位管理](/position.png) |
| 角色管理  | ![角色管理](/role.png) |
| 用户管理  | ![用户管理](/user.png) |
| 日志管理  | ![日志管理](/log.png) |
| 配置管理  | ![配置管理](/config.png) |
| 在线用户  | ![在线用户](/online.png) |
| 服务器监控 | ![服务器监控](/service.png) |
| 缓存监控  | ![缓存监控](/cache.png) |
| 任务管理  | ![任务管理](/job.png) |
| 字典管理  | ![字典管理](/dict.png) |
| 接口管理  | ![接口管理](/docs.png) |
| 系统主题  | ![系统主题](/theme.png) |
| 在线文档  | ![在线文档](/help.png) |
| 系统锁屏  | ![系统锁屏](/lock.png) |
| 表单构建  | ![表单构建](/form.png) |
| 代码生成  | ![代码生成](/gencode.png) |
| 流程管理  | ![流程管理](/workflow.png) |
| 文件管理  | ![文件管理](/file.png) |
| 我的应用  | ![我的应用](/myapp.png) |
| 配置中心  | ![配置中心](/setting.png) |
| 智能助手  | ![智能助手](/ai.png) |

### 移动端

| 模块 <div style="width:60px"/> | 详情 | 模块 <div style="width:60px"/> | 详情 | 模块 <div style="width:60px"/> | 详情 |
|----------|------|----------|------|----------|------|
| 登录    | ![移动端登录](/app_login.png) | 首页      | ![移动端首页](/app_home.png) | 我的      | ![移动端个人中心](/app_mine.png) |
| 个人  | ![移动端个人信息](/app_profile.png) | 设置   | ![移动端设置](/app_setting.png) | 工作台      | ![移动端工作台](/app_work.png) |

## 🚀二开教程

### 后端部分（FastapiAdmin 主工程）

1. **编写实体类层**：在 `FastapiAdmin/backend/app/api/v1/models/demo/example_model.py` 中创建 example 的 ORM 模型（对应 Spring Boot 中的实体类层）
2. **编写数据模型层**：在 `FastapiAdmin/backend/app/api/v1/schemas/demo/example_schema.py` 中创建 example 数据模型（对应 Spring Boot 中的 DTO 层）
3. **编写查询参数模型层**：在 `FastapiAdmin/backend/app/api/v1/params/demo/example_param.py` 中创建 example 的查询参数模型（对应 Spring Boot 中的 DTO 层）
4. **编写持久化层**：在 `FastapiAdmin/backend/app/api/v1/cruds/demo/example_crud.py` 中创建 example 数据层（对应 Spring Boot 中的 Mapper 或 DAO 层）
5. **编写业务层**：在 `FastapiAdmin/backend/app/api/v1/services/demo/example_service.py` 中创建 example 数据层（对应 Spring Boot 中的 Service 层）
6. **编写接口层**：在 `FastapiAdmin/backend/app/api/v1/controllers/demo/example_controller.py` 中创建 example 数据层（对应 Spring Boot 中的 Controller 层）
7. **注册后端路由**：在 `FastapiAdmin/backend/app/api/v1/urls/demo/example_url.py` 中注册 example 路由
8. **注册路由到 FastAPI 服务中**：在 `FastapiAdmin/backend/plugin/init_app.py` 中注册路由
9. **将 demo 模块添加至系统初始化脚本**：在 `FastapiAdmin/backend/app/scripts/initialize.py` 中添加（如果需要可以把 demo 的菜单权限，配置到 `FastapiAdmin/backend/app/scripts/data/system_menu.json` 和 `FastapiAdmin/backend/app/scripts/data/system_role_menus.json` 或从前端页面菜单中新增）
10. **将 demo 模块添加至数据库迁移脚本中**：在 `FastapiAdmin/backend/app/alembic/env.py` 中添加

### 前端部分（FastapiAdmin 主工程）

1. **前端接入后端接口地址**：在 `FastapiAdmin/frontend/src/api/demo/example.ts` 中配置
2. **编写前端页面**：在 `FastapiAdmin/frontend/src/views/demo/example/index.vue` 中编写

### 移动端部分（FastApp 移动端）

1. **移动端接入后端接口地址**：在 `FastApp/src/api` 中编写
2. **编写移动端页面**：在 `FastApp/src/pages` 中编写

## 💡常见问题及解决方案

### 1. 后端启动失败

**问题**：数据库连接失败
**解决方案**：检查环境配置文件中的数据库连接信息是否正确，确保数据库服务正在运行，且用户名密码正确。

**问题**：Redis连接失败
**解决方案**：检查环境配置文件中的Redis连接信息是否正确，确保Redis服务正在运行。

**问题**：依赖安装失败
**解决方案**：确保Python版本正确（>=3.10），可以尝试使用虚拟环境重新安装依赖。

### 2. 前端启动失败

**问题**：依赖安装失败
**解决方案**：确保Node.js版本正确（>=20.0），可以尝试清除缓存后重新安装：`pnpm cache clean && pnpm install`。

**问题**：API请求失败
**解决方案**：检查前端环境配置文件中的API基础URL是否正确，确保后端服务正在运行。

### 3. 部署问题

**问题**：Docker部署失败
**解决方案**：确保服务器已安装Docker和Docker Compose，检查端口是否被占用，查看容器日志了解具体错误信息。

**问题**：Nginx配置错误
**解决方案**：检查Nginx配置文件中的反向代理设置是否正确，确保后端服务地址配置正确。

### 4. 其他问题

**问题**：系统初始化失败
**解决方案**：确保数据库已正确初始化，且迁移已应用，可以尝试重新执行初始化命令：`python main.py init`。

**问题**：权限不足
**解决方案**：检查用户角色权限设置，确保当前用户有足够的权限访问所需功能。
