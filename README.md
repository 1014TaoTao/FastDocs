# FastDocs

FastDocs是FastapiAdmin 官网文档，该项目是一套完全开源的快速开发平台，提供免费使用。它结合了现代、高性能的技术栈，后端采用Fastapi + SQLAlchemy，前端采用基于 vue3 + typescript + vite + pinia + Element-Plus。旨在帮助开发者快速搭建高质量的中后台系统。

## 项目结构

```sh
FastDocs/
├─ .vitepress           # 静态资源文件
│  ├─ cache             # 缓存
│  ├─ theme             # 主题
│  └─ config.ts         # 配置文件
├─ src                  # 源代码
│  ├─ development/      # 开发文档
│  │  ├─ backend.md     # 后端文档
│  │  └─ frontend.md    # 前端文档
│  ├─ index.md          # 首页
│  ├─ overview/         # 概述文档
│  │  ├─ about.md       # 关于
│  │  ├─ overview.md    # 概述
│  │  └─ why.md         # 为什么选择
│  ├─ public/           # 公共资源
│  └─ quickstart/       # 快速开始
│     └─ start.md       # 开始指南
├─ LICENSE              # 许可证
├─ package.json         # 项目依赖文件
└─ README.md            # 项目说明文档

```

## 🔗 源码仓库

| 平台 | 仓库地址 |
|------|----------|
| GitHub | [FastapiAdmin主工程](https://github.com/1014TaoTao/FastapiAdmin.git) \| [FastDocs官网](https://github.com/1014TaoTao/FastDocs.git) \| [FastApp移动端](https://github.com/1014TaoTao/FastApp.git) |
| Gitee  | [FastapiAdmin主工程](https://gitee.com/tao__tao/FastapiAdmin.git) \| [FastDocs官网](https://gitee.com/tao__tao/FastDocs.git) \| [FastApp移动端](https://gitee.com/tao__tao/FastApp.git) |

## 官网展示

![在线文档](https://gitee.com/tao__tao/FastDocs/raw/main/src/public/help.png)

## 快速开始

```sh
# 进入项目目录
cd FastDocs
# 安装依赖
pnpm install
# 运行文档工程
pnpm run docs:dev
# 构建文档工程
pnpm run docs:build
```
