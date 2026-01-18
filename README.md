# FastDocs

FastDocs是FastapiAdmin 官网文档，该项目是一套完全开源的快速开发平台，提供免费使用。它结合了现代、高性能的技术栈，后端采用Fastapi + SQLAlchemy，前端采用基于 vue3 + typescript + vite + pinia + Element-Plus。旨在帮助开发者快速搭建高质量的中后台系统。

## 项目结构

```sh
FastDocs/
├─ .vitepress           # VitePress配置
│  ├─ theme             # 主题配置
│  │  ├─ index.ts       # 主题入口
│  │  └─ style.css      # 主题样式
│  └─ config.ts         # 主配置文件
├─ src                  # 源代码
│  ├─ en                # 英文文档
│  │  ├─ development/   # 开发文档
│  │  ├─ overview/      # 概述文档
│  │  ├─ quickstart/    # 快速开始
│  │  └─ index.md       # 英文首页
│  ├─ zh                # 中文文档
│  │  ├─ development/   # 开发文档
│  │  ├─ overview/      # 概述文档
│  │  ├─ quickstart/    # 快速开始
│  │  └─ index.md       # 中文首页
│  ├─ public/           # 公共资源
│  └─ index.md          # 重定向首页
├─ .eslintrc.js         # ESLint配置
├─ .prettierrc.js       # Prettier配置
├─ .gitignore           # Git忽略文件
├─ LICENSE              # 许可证
├─ package.json         # 项目依赖文件
└─ README.md            # 项目说明文档

```

## 🔗 源码仓库

| 平台 | 仓库地址 |
|------|----------|
| GitHub | [FastapiAdmin主工程](https://github.com/fastapiadmin/FastapiAdmin.git) \| [FastDocs官网](https://github.com/fastapiadmin/FastDocs.git) \| [FastApp移动端](https://github.com/fastapiadmin/FastApp.git) |
| Gitee  | [FastapiAdmin主工程](https://gitee.com/fastapiadmin/FastapiAdmin.git) \| [FastDocs官网](https://gitee.com/fastapiadmin/FastDocs.git) \| [FastApp移动端](https://gitee.com/fastapiadmin/FastApp.git) |

## 官网展示

![在线文档](https://gitee.com/fastapiadmin/FastDocs/raw/main/docs/public/help.png)

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
