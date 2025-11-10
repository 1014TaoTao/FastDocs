---
title: 小程序开发指南
---
# FastApp 小程序开发指南

## 📖 项目介绍

### 项目概述

**FastApp** 是 FastapiAdmin 项目的移动端应用，基于 uni-app 框架开发，支持一套代码多端运行。采用 Vue 3 + TypeScript + Vite 等现代化技术栈，集成了完善的代码规范和开发工具链，为开发者提供开箱即用的移动端开发解决方案。

### 核心特点

- 🚀 **跨平台支持** - 一套代码，多端运行（H5、微信小程序、支付宝小程序、App等）
- 💎 **现代化技术栈** - Vue 3 Composition API + TypeScript + Vite
- 🎨 **精美UI组件** - 集成 wot-design-uni 组件库，开箱即用
- 📦 **工程化配置** - ESLint、Prettier、Stylelint、Husky 等工具链
- 🔥 **开发体验** - 自动导入、类型提示、热更新等
- 📱 **完整功能** - 用户管理、数据统计、工作台、个人中心等
- 🌙 **主题切换** - 支持深色/浅色主题切换，6种主题色可选

### 核心功能模块

- ✅ **用户认证** - 登录、注册、密码重置、权限管理
- ✅ **首页展示** - 轮播图、快捷导航、通知公告、数据统计
- ✅ **工作台** - 业务功能入口，支持权限控制
- ✅ **个人中心** - 个人信息、设置、FAQ、问题反馈
- ✅ **数据统计** - 实时访客数、浏览量等数据展示
- ✅ **主题切换** - 支持深色/浅色主题切换，6种主题色可选

## 🏗️ 技术栈

### 核心框架

- **[uni-app](https://uniapp.dcloud.net.cn/)** - 跨平台应用开发框架
- **[Vue 3](https://cn.vuejs.org/)** - 渐进式 JavaScript 框架（Composition API）
- **[TypeScript](https://www.typescriptlang.org/)** - JavaScript 的超集，提供类型支持
- **[Vite](https://cn.vitejs.dev/)** - 下一代前端构建工具

### UI 组件库

- **[wot-design-uni](https://wot-design-uni.netlify.app/)** - 基于 uni-app 的组件库

### 工具库

- **[UnoCSS](https://unocss.dev/)** - 原子化 CSS 引擎
- **[VueUse](https://vueuse.org/)** - Vue Composition API 工具集合
- **[vue-i18n](https://vue-i18n.intlify.dev/)** - Vue 国际化插件
- **[@stomp/stompjs](https://stomp-js.github.io/)** - WebSocket 消息协议库

### 状态管理

- **[Pinia](https://pinia.vuejs.org/)** - Vue3 官方状态管理库

### 开发工具

- **ESLint** - JavaScript/TypeScript 代码检查工具
- **Prettier** - 代码格式化工具
- **Stylelint** - CSS 代码检查工具
- **Husky** - Git hooks 工具
- **Commitlint** - Git 提交信息规范检查

## 📁 项目结构

### 完整目录结构

```
FastApp/
├── public/                 # 静态资源目录
├── src/
│   ├── api/               # API 接口定义
│   ├── components/        # 公共组件
│   ├── composables/       # 组合式函数
│   ├── constants/         # 常量定义
│   ├── enums/             # 枚举定义
│   ├── layouts/           # 布局组件
│   │   ├── default.vue    # 默认布局（应用主题）
│   │   └── tabbar.vue    # 底部导航布局（应用主题）
│   ├── pages/             # 页面目录
│   │   ├── index/         # 首页
│   │   ├── login/         # 登录页
│   │   ├── work/          # 工作台
│   │   └── mine/          # 个人中心
│   │       └── settings/  # 设置页面
│   │           └── theme/ # 主题设置页面
│   ├── router/            # 路由配置
│   ├── store/             # 状态管理
│   │   └── modules/
│   │       └── theme.store.ts  # 主题状态管理（核心）
│   ├── styles/            # 样式文件
│   │   └── index.scss     # 全局 CSS 变量定义
│   ├── types/             # TypeScript 类型定义
│   ├── utils/             # 工具函数
│   │   └── color.ts       # 颜色处理工具函数
│   ├── App.vue            # 应用根组件（初始化主题）
│   ├── main.ts            # 应用入口文件
│   ├── manifest.json      # 应用配置文件
│   └── pages.json         # 页面路由配置
├── theme.json             # uni-app 主题配置（小程序）
├── dist/                  # 构建输出目录
├── .eslintrc.js           # ESLint 配置
├── vite.config.ts         # Vite 配置
├── tsconfig.json          # TypeScript 配置
├── pages.config.ts        # 页面配置
├── unocss.config.ts       # UnoCSS 配置
└── package.json           # 项目依赖配置
```

## 🚀 快速开始

### 环境要求

- **Node.js** >= 22
- **pnpm** >= 9

### 安装依赖

```bash
pnpm install
```

### 开发运行

#### H5 开发

```bash
# 启动 H5 开发服务器
pnpm run dev:h5

# 访问地址
# http://localhost:5180/app
```

#### 微信小程序开发

```bash
# 启动微信小程序开发
pnpm run dev:mp-weixin

# 使用微信开发者工具打开 dist/dev/mp-weixin 目录
```

#### 支付宝小程序开发

```bash
# 启动支付宝小程序开发
pnpm run dev:mp-alipay

# 使用支付宝开发者工具打开 dist/dev/mp-alipay 目录
```

### 生产构建

#### H5 构建

```bash
pnpm run build:h5

# 构建产物在 dist/build/h5 目录
```

#### 微信小程序构建

```bash
pnpm run build:mp-weixin

# 构建产物在 dist/build/mp-weixin 目录
# ⚠️ 注意：此功能未测试
```

#### 支付宝小程序构建

```bash
pnpm run build:mp-alipay

# 构建产物在 dist/build/mp-alipay 目录
# ⚠️ 注意：此功能未测试
```

## ⚙️ 环境配置

### 环境变量说明

在项目根目录创建 `.env` 文件配置环境变量：

```env
# API 基础地址
VITE_API_BASE_URL=http://localhost:8001

# API 前缀
VITE_APP_BASE_API=/api

# 开发服务器端口
VITE_APP_PORT=5180
```

### 代理配置

H5 开发时的代理配置在 `vite.config.ts` 中：

```typescript
proxy: {
  [env.VITE_APP_BASE_API]: {
    changeOrigin: true,
    target: env.VITE_API_BASE_URL,
  },
}
```

## 🎨 主题切换与全局颜色设置

FastApp 项目实现了完整的主题切换和全局颜色管理系统，支持：

- ✅ **双主题模式**：浅色模式（Light）和深色模式（Dark）
- ✅ **自定义主题色**：6 种预设主题色，支持动态切换
- ✅ **持久化存储**：主题设置自动保存到本地存储
- ✅ **跨平台兼容**：支持 H5、小程序、App 等多端
- ✅ **组件库集成**：与 wot-design-uni 组件库深度集成
- ✅ **响应式更新**：主题切换后自动更新所有相关组件

### 架构设计

#### 核心文件结构

```
FastApp/
├── src/
│   ├── store/
│   │   └── modules/
│   │       └── theme.store.ts      # 主题状态管理（核心）
│   ├── styles/
│   │   └── index.scss               # 全局 CSS 变量定义
│   ├── utils/
│   │   └── color.ts                 # 颜色处理工具函数
│   ├── layouts/
│   │   ├── default.vue              # 默认布局（应用主题）
│   │   └── tabbar.vue               # 底部导航布局（应用主题）
│   ├── pages/
│   │   └── mine/
│   │       └── settings/
│   │           └── theme/
│   │               └── index.vue    # 主题设置页面
│   └── App.vue                      # 应用入口（初始化主题）
├── theme.json                       # uni-app 主题配置（小程序）
└── src/theme.json                   # 主题配置副本
```

#### 数据流向

```
用户操作
  ↓
主题设置页面 (theme/index.vue)
  ↓
主题 Store (theme.store.ts)
  ↓
├─→ 更新 CSS 变量 (updateCSSVariables)
├─→ 更新组件库主题 (themeVars)
├─→ 更新导航栏颜色 (setCustomNavigationBarColor)
└─→ 持久化存储 (useUniStorage)
  ↓
ConfigProvider 组件
  ↓
全局应用主题
```

### 主题状态管理

#### 核心 Store：`src/store/modules/theme.store.ts`

主题状态管理使用 Pinia 实现，提供了完整的主题管理功能。

##### 1. 主题模式类型

```typescript
export type ThemeMode = "light" | "dark";
```

##### 2. 主题色选项

预定义了 6 种主题色：

```typescript
const themeColorOptions: ThemeColorOption[] = [
  { name: "默认蓝", value: "blue", primary: "#4D7FFF" },
  { name: "活力橙", value: "orange", primary: "#FF7D00" },
  { name: "薄荷绿", value: "green", primary: "#07C160" },
  { name: "樱花粉", value: "pink", primary: "#FF69B4" },
  { name: "紫罗兰", value: "purple", primary: "#8A2BE2" },
  { name: "朱砂红", value: "red", primary: "#FF4757" },
];
```

##### 3. 持久化存储

使用自定义的 `useUniStorage` 函数实现响应式存储：

```typescript
// 主题模式存储
const theme = useUniStorage<ThemeMode>("app-theme", "dark");

// 主题色存储
const currentThemeColor = useUniStorage<ThemeColorOption>(
  "app-theme-color",
  themeColorOptions[0],
);
```

**特性：**
- 自动同步到 `uni.setStorageSync`
- 支持复杂对象（自动 JSON 序列化）
- 响应式更新，值变化时自动保存

##### 4. 核心方法

**`toggleTheme(mode?: ThemeMode)`** - 切换主题模式：

```typescript
// 自动切换（light ↔ dark）
themeStore.toggleTheme();

// 指定模式
themeStore.toggleTheme("dark");
themeStore.toggleTheme("light");
```

**`setCurrentThemeColor(color: ThemeColorOption)`** - 设置主题色：

```typescript
themeStore.setCurrentThemeColor({
  name: "活力橙",
  value: "orange",
  primary: "#FF7D00"
});
```

**`initTheme()`** - 初始化主题（在应用启动时调用）：

```typescript
// 在 App.vue 中
onLaunch(() => {
  themeStore.initTheme();
});
```

### 全局颜色配置

#### 1. CSS 变量定义：`src/styles/index.scss`

全局 CSS 变量分为三个部分：

**基础变量（`:root`）**

```scss
:root {
  /* 主题色系 */
  --primary-color: #165dff;
  --primary-color-light: #94bfff;
  --primary-color-dark: #0e3c9b;
  --wot-color-theme: #165dff;

  /* 功能色系 */
  --success-color: #07c160;
  --warning-color: #ff7d00;
  --danger-color: #f53f3f;
  --info-color: #86909c;

  /* 文字颜色 */
  --text-color: #1d2129;
  --text-color-2: #4e5969;
  --text-color-3: #86909c;
  --text-color-placeholder: #c9cdd4;
  --text-color-inverse: #ffffff;

  /* 背景颜色 */
  --bg-color: #ffffff;
  --bg-color-2: #f8f8f8;
  --bg-color-3: #f2f3f5;
  --card-bg-color: #ffffff;

  /* 边框颜色 */
  --border-color: #e5e6eb;
  --border-color-light: #f2f3f5;
}
```

**暗黑模式变量（`.dark`）**

```scss
.dark {
  --text-color: #ffffff;
  --text-color-2: #e0e0e0;
  --text-color-3: #a0a0a0;
  --text-color-placeholder: #606060;
  --text-color-inverse: #1d2129;

  --bg-color: #0f0f0f;
  --bg-color-2: #1a1a1a;
  --bg-color-3: #242424;
  --card-bg-color: #1a1a1a;

  --border-color: #2f2f2f;
  --border-color-light: #3d3d3d;
}
```

#### 2. 动态 CSS 变量更新

在 `theme.store.ts` 的 `updateCSSVariables()` 方法中，动态更新 CSS 变量：

```typescript
const updateCSSVariables = () => {
  const isDark = theme.value === "dark";
  const primaryColor = currentThemeColor.value.primary;

  // 计算颜色变体
  const primaryColorLight = adjustColorBrightness(primaryColor, 1.5);
  const primaryColorDark = adjustColorBrightness(primaryColor, 0.6);

  // H5 环境：更新 :root 的 CSS 变量
  // #ifdef H5
  if (typeof document !== "undefined") {
    const root = document.documentElement;
    root.style.setProperty("--wot-color-theme", primaryColor);
    root.style.setProperty("--primary-color", primaryColor);
    root.style.setProperty("--primary-color-light", primaryColorLight);
    root.style.setProperty("--primary-color-dark", primaryColorDark);
    root.classList.toggle("dark", isDark);
    root.classList.toggle("light", !isDark);
  }
  // #endif
};
```

#### 3. uni-app 主题配置：`theme.json`

用于小程序的原生主题配置：

```json
{
  "light": {
    "bgColor": "#F8F8F8",
    "bgColorBottom": "#F8F8F8",
    "bgColorTop": "#F8F8F8",
    "bgTxtStyle": "dark",
    "navBgColor": "#FFF",
    "navTxtStyle": "black",
    "tabBgColor": "#ffffff",
    "tabBorderStyle": "black",
    "tabColor": "#bfbfbf",
    "tabSelectedColor": "#0165FF"
  },
  "dark": {
    "bgColor": "#000",
    "bgColorBottom": "#000",
    "bgColorTop": "#000",
    "bgTxtStyle": "light",
    "navBgColor": "#000000",
    "navTxtStyle": "white",
    "tabBgColor": "#1a1a1a",
    "tabBorderStyle": "white",
    "tabColor": "#bfbfbf",
    "tabSelectedColor": "#0165FF"
  }
}
```

### 颜色工具函数

#### 文件：`src/utils/color.ts`

提供了三个核心颜色处理函数：

**`hexToRgb(hex: string)`** - 将十六进制颜色转换为 RGB：

```typescript
const rgb = hexToRgb("#4D7FFF");
// { r: 77, g: 127, b: 255 }
```

**`rgbToHex(r: number, g: number, b: number)`** - 将 RGB 转换为十六进制：

```typescript
const hex = rgbToHex(77, 127, 255);
// "#4d7fff"
```

**`adjustColorBrightness(hex: string, factor: number)`** - 调整颜色亮度：

```typescript
// 变亮（factor > 1）
const lighter = adjustColorBrightness("#4D7FFF", 1.5);
// "#75BFFF"

// 变暗（factor < 1）
const darker = adjustColorBrightness("#4D7FFF", 0.6);
// "#2E4C99"
```

### 使用指南

#### 1. 在组件中使用主题

**方式一：使用 CSS 变量**

```vue
<template>
  <view class="my-component">
    <text class="title">标题</text>
    <text class="content">内容</text>
  </view>
</template>

<style lang="scss" scoped>
.my-component {
  background-color: var(--bg-color);
  border: 1px solid var(--border-color);
  
  .title {
    color: var(--text-color);
  }
  
  .content {
    color: var(--text-color-2);
  }
}
</style>
```

**方式二：使用主题 Store**

```vue
<script setup lang="ts">
import { useThemeStore } from "@/store";

const themeStore = useThemeStore();

// 获取当前主题模式
const isDark = themeStore.isDark;

// 获取当前主题色
const primaryColor = themeStore.currentThemeColor.primary;

// 切换主题
const handleToggle = () => {
  themeStore.toggleTheme();
};
</script>

<template>
  <view :style="{ color: themeStore.themeVars.colorTitle }">
    内容
  </view>
</template>
```

#### 2. 在组件库中使用主题

通过 `wd-config-provider` 组件传递主题变量：

```vue
<template>
  <wd-config-provider
    :theme-vars="themeVars"
    :theme="theme"
  >
    <wd-button type="primary">按钮</wd-button>
    <wd-card title="卡片">内容</wd-card>
  </wd-config-provider>
</template>

<script setup lang="ts">
import { useThemeStore } from "@/store";

const themeStore = useThemeStore();
const theme = computed(() => themeStore.theme);
const themeVars = computed(() => themeStore.themeVars);
</script>
```

## 📝 开发指南

### 代码规范

项目集成了完善的代码规范工具：

```bash
# ESLint 检查并自动修复
pnpm run lint:eslint

# Prettier 格式化
pnpm run lint:prettier

# Stylelint 检查样式
pnpm run lint:stylelint

# TypeScript 类型检查
pnpm run type-check
```

### 自动导入

项目配置了自动导入，以下内容无需手动导入：

- Vue 3 API（`ref`, `computed`, `watch` 等）
- uni-app API（`uni.request`, `uni.navigateTo` 等）
- Pinia（`defineStore`, `storeToRefs` 等）
- 路由（`useRouter`, `useRoute` 等）
- 组件库工具（`useToast`, `useMessage` 等）
- `src/composables` 目录下的组合式函数
- `src/utils` 目录下的工具函数
- `src/api` 目录下的 API 函数

### 路由配置

路由配置采用约定式路由，在 `src/pages` 目录下创建页面文件即可自动生成路由。

页面路由配置在 `pages.config.ts` 文件中：

```typescript
export default defineUniPages({
  globalStyle: {
    navigationBarTitleText: "FastApp",
    // ...
  },
  tabBar: {
    // 底部导航栏配置
  },
});
```

### 状态管理

使用 Pinia 进行状态管理，store 文件位于 `src/store` 目录：

```typescript
import { defineStore } from 'pinia'

export const useUserStore = defineStore('user', {
  state: () => ({
    // 状态
  }),
  actions: {
    // 方法
  }
})
```

### 样式开发

- 使用 **UnoCSS** 原子化 CSS，支持类名方式快速开发
- 支持 **SCSS** 预处理器
- 支持主题变量配置（`src/theme.json`）

### API 请求

API 请求封装在 `src/api` 目录，使用 uni-app 的 `uni.request` 进行网络请求。

## 📦 构建部署

### H5 部署

1. 执行构建命令：`pnpm run build:h5`
2. 将 `dist/build/h5` 目录部署到 Web 服务器
3. 配置服务器支持 SPA 路由（如 Nginx 的 `try_files`）

### 小程序发布

1. 执行对应平台的构建命令
   - 微信小程序：`pnpm run build:mp-weixin`
   - 支付宝小程序：`pnpm run build:mp-alipay`
2. 使用对应平台的开发者工具打开构建产物目录
3. 在开发者工具中上传代码并提交审核

### App 打包

1. 使用 HBuilderX 打开项目
2. 配置 App 相关信息（图标、启动页等）
3. 选择云打包或本地打包
4. 下载安装包并发布到应用商店

## 🎯 最佳实践

### 1. 颜色使用规范

✅ **推荐：**
- 使用 CSS 变量而非硬编码颜色值
- 使用语义化的变量名（如 `--text-color` 而非 `--color-1`）
- 在暗黑模式下覆盖变量值

❌ **不推荐：**
```scss
// 硬编码颜色
.title { color: #1d2129; }

// 非语义化变量
.text { color: var(--color-1); }
```

### 2. 主题切换时机

✅ **推荐：**
- 在设置页面提供主题切换入口
- 切换后显示提示信息
- 重启应用确保一致性

❌ **不推荐：**
- 频繁切换主题（影响性能）
- 切换后不重启应用（可能导致不一致）

### 3. 组件开发规范

✅ **推荐：**
- 组件样式使用 CSS 变量
- 支持主题适配类（如 `.theme-adaptive`）
- 测试浅色和深色两种模式

❌ **不推荐：**
- 组件内部硬编码颜色
- 忽略暗黑模式适配

### 4. 性能优化

- 使用 `computed` 缓存主题相关计算
- 避免在模板中频繁访问 `themeStore`
- CSS 变量更新使用批量操作

## 📚 学习路径

1. **新手入门** - 阅读快速开始和项目结构
2. **功能开发** - 学习主题系统和API接口管理
3. **高级特性** - 掌握性能优化和跨平台适配
4. **生产部署** - 完成项目上线

## 🔗 相关资源

### 源码仓库

| 平台 | 仓库地址 |
|------|----------|
| **GitHub** | [FastApp移动端](https://github.com/1014TaoTao/FastApp.git) |
| **Gitee**  | [FastApp移动端](https://gitee.com/tao__tao/FastApp.git) |

### 官方文档

- [uni-app 官方文档](https://uniapp.dcloud.net.cn/)
- [Vue 3 官方文档](https://cn.vuejs.org/)
- [wot-design-uni 组件库](https://wot-design-uni.netlify.app/)
- [Pinia 官方文档](https://pinia.vuejs.org/)

---

**文档版本：** 1.0.0  
**最后更新：** 2025年11月10日

