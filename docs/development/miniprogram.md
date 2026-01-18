---
outline: "deep"
title: FastApp 移动端开发指南
---
# FastApp 移动端开发指南

## 📱项目概述

**FastApp** 是 FastapiAdmin 项目的移动端应用，基于 **Uni App** 框架开发，支持多平台部署（包括微信小程序、H5、iOS、Android 等）。

### 核心功能

- **用户认证**：登录、注册、忘记密码等
- **工作台**：常用功能快速入口
- **个人中心**：用户信息管理、设置等
- **消息通知**：系统消息、通知中心
- **数据统计**：业务数据可视化展示
- **离线缓存**：支持离线访问部分功能

## 🛠️技术栈

| 技术 | 版本 | 说明 |
|------|------|------|
| Uni App | 3.0.0+ | 跨平台移动端开发框架 |
| Vue3 | 3.3+ | 前端框架 |
| TypeScript | 5.0+ | 类型系统 |
| Pinia | 2.1+ | 状态管理 |
| Wot Design Uni | 1.9.1+ | UI 组件库 |
| Vite | 5.0+ | 构建工具 |
| Axios | 1.6+ | HTTP 客户端 |

## 📁项目结构

```
FastApp/
├─ public/             # 静态资源
│  ├─ favicon.png      # 网站图标
├─ src/                # 源代码
│  ├─ api/             # API 接口
│  │  ├─ auth.ts       # 认证相关接口
│  │  ├─ file.ts       # 文件相关接口
│  │  └─ user.ts       # 用户相关接口
│  ├─ components/      # 组件
│  │  ├─ cu-date-query/ # 日期查询组件
│  │  ├─ cu-picker/     # 选择器组件
│  │  ├─ qiun-error/    # 错误提示组件
│  │  └─ qiun-loading/  # 加载组件
│  ├─ composables/     # 组合式 API
│  │  ├─ useNavigationBar.ts # 导航栏管理
│  │  ├─ useStomp.ts   # WebSocket 管理
│  │  └─ useTabbar.ts  # 标签栏管理
│  ├─ constants/       # 常量
│  │  ├─ index.ts      # 常量定义
│  │  └─ storage.constant.ts # 存储键名
│  ├─ enums/           # 枚举
│  │  ├─ api-code.enum.ts # API 错误码
│  │  └─ api-header.enum.ts # API 头部
│  ├─ layouts/         # 布局
│  │  ├─ default.vue   # 默认布局
│  │  └─ tabbar.vue    # 标签栏布局
│  ├─ pages/           # 页面
│  │  ├─ index/        # 首页
│  │  ├─ login/        # 登录页
│  │  ├─ mine/         # 个人中心
│  │  └─ work/         # 工作台
│  ├─ router/          # 路由
│  │  └─ index.ts      # 路由配置
│  ├─ static/          # 静态资源
│  │  ├─ icons/        # 图标
│  │  ├─ images/       # 图片
│  │  └─ logo.png      # Logo
│  ├─ store/           # 状态管理
│  │  ├─ modules/      # 模块
│  │  │  ├─ theme.store.ts # 主题管理
│  │  │  └─ user.store.ts # 用户管理
│  │  └─ index.ts      # 状态管理配置
│  ├─ styles/          # 样式
│  │  └─ index.scss    # 全局样式
│  ├─ types/           # 类型定义
│  ├─ utils/           # 工具函数
│  │  ├─ auth.ts       # 认证工具
│  │  ├─ color.ts      # 颜色工具
│  │  ├─ index.ts      # 工具函数
│  │  ├─ request.ts    # 请求工具
│  │  └─ storage.ts    # 存储工具
│  ├─ App.vue          # 应用入口
│  ├─ main.ts          # 主文件
│  ├─ manifest.json    # 应用配置
│  ├─ pages.json       # 页面配置
│  └─ theme.json       # 主题配置
├─ .env.development    # 开发环境配置
├─ .env.production     # 生产环境配置
├─ package.json        # 项目依赖
└─ vite.config.ts      # Vite 配置
```

## 🔧环境搭建

### 1. 安装开发工具

- **Node.js**：版本 >= 20.0（推荐使用最新版）
- **HBuilderX**：Uni App 官方推荐的开发工具（可选，也可以使用 VS Code + 插件）
- **微信开发者工具**：用于微信小程序开发和调试

### 2. 安装依赖

```sh
# 进入项目目录
cd FastApp

# 安装 pnpm（如果未安装）
npm install -g pnpm

# 安装项目依赖
pnpm install
```

### 3. 配置环境变量

```sh
# 复制环境配置文件
cp .env.development.example .env.development
cp .env.production.example .env.production

# 编辑环境配置文件
# 主要配置项：
# - VITE_API_BASE_URL: API 基础 URL
# - VITE_APP_TITLE: 应用标题
# - VITE_APP_VERSION: 应用版本
```

## 🚀开发流程

### 1. 启动开发服务器

#### H5 开发

```sh
# 启动 H5 开发服务器
pnpm run dev:h5

# 浏览器访问：http://localhost:5174
```

#### 微信小程序开发

```sh
# 启动微信小程序开发服务器
pnpm run dev:mp-weixin

# 在微信开发者工具中导入项目目录：FastApp/dist/dev/mp-weixin
```

#### 其他平台开发

```sh
# 启动支付宝小程序开发服务器
pnpm run dev:mp-alipay

# 启动百度小程序开发服务器
pnpm run dev:mp-baidu

# 启动字节跳动小程序开发服务器
pnpm run dev:mp-toutiao

# 启动 QQ 小程序开发服务器
pnpm run dev:mp-qq
```

### 2. 构建发布

#### 构建 H5

```sh
# 构建 H5 版本
pnpm run build:h5

# 构建产物：FastApp/dist/build/h5
```

#### 构建微信小程序

```sh
# 构建微信小程序版本
pnpm run build:mp-weixin

# 构建产物：FastApp/dist/build/mp-weixin
# 在微信开发者工具中上传代码
```

#### 构建其他平台

```sh
# 构建支付宝小程序
pnpm run build:mp-alipay

# 构建百度小程序
pnpm run build:mp-baidu

# 构建字节跳动小程序
pnpm run build:mp-toutiao

# 构建 QQ 小程序
pnpm run build:mp-qq
```

## 📚页面开发

### 1. 创建新页面

1. **在 `pages.json` 中添加页面配置**：

```json
{
  "pages": [
    {
      "path": "pages/index/index",
      "style": {
        "navigationBarTitleText": "首页"
      }
    },
    // 其他页面...
  ]
}
```

2. **创建页面文件**：

```
FastApp/src/pages/
└─ new-page/
   ├─ index.vue      # 页面组件
   ├─ data.ts        # 数据定义（可选）
   └─ types.ts       # 类型定义（可选）
```

3. **页面示例**：

```vue
<template>
  <view class="page">
    <view class="title">新页面</view>
    <view class="content">
      <text>{{ message }}</text>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const message = ref('Hello FastApp!');
</script>

<style scoped>
.page {
  padding: 20rpx;
}

.title {
  font-size: 32rpx;
  font-weight: bold;
  margin-bottom: 20rpx;
}

.content {
  font-size: 28rpx;
  color: #666;
}
</style>
```

### 2. 路由管理

#### 页面跳转

```typescript
// 普通跳转
uni.navigateTo({
  url: '/pages/new-page/index'
});

// 带参数跳转
uni.navigateTo({
  url: '/pages/new-page/index?id=1&name=test'
});

// 重定向跳转
uni.redirectTo({
  url: '/pages/new-page/index'
});

// 跳转到 tabBar 页面
uni.switchTab({
  url: '/pages/index/index'
});

// 关闭所有页面，打开新页面
uni.reLaunch({
  url: '/pages/new-page/index'
});
```

#### 接收参数

```typescript
// 在页面 onLoad 生命周期中接收参数
import { onLoad } from '@dcloudio/uni-app';

onLoad((options) => {
  console.log('参数：', options);
  // options.id, options.name
});
```

## 📡API 调用

### 1. 封装的 API 工具

FastApp 使用封装的 `request.ts` 工具进行 API 调用，支持自动添加认证 token、错误处理等功能。

### 2. API 接口定义

API 接口定义在 `src/api` 目录下，按模块分类：

```typescript
// src/api/user.ts 示例
import request from '../utils/request';

export const userApi = {
  // 获取用户信息
  getUserInfo: () => {
    return request({
      url: '/api/v1/user/info',
      method: 'GET'
    });
  },
  
  // 更新用户信息
  updateUserInfo: (data: any) => {
    return request({
      url: '/api/v1/user/update',
      method: 'POST',
      data
    });
  }
};
```

### 3. 调用 API

```typescript
import { userApi } from '../api/user';

// 调用 API
const getUserInfo = async () => {
  try {
    const res = await userApi.getUserInfo();
    console.log('用户信息：', res.data);
  } catch (error) {
    console.error('获取用户信息失败：', error);
  }
};

// 调用更新用户信息 API
const updateUser = async () => {
  try {
    const res = await userApi.updateUserInfo({
      name: '新名字',
      avatar: '新头像'
    });
    console.log('更新成功：', res.data);
  } catch (error) {
    console.error('更新失败：', error);
  }
};
```

## 🔐认证管理

### 1. 登录流程

1. **调用登录 API**：

```typescript
import { authApi } from '../api/auth';
import { useUserStore } from '../store/modules/user.store';

const userStore = useUserStore();

const login = async (username: string, password: string) => {
  try {
    const res = await authApi.login({
      username,
      password
    });
    
    // 保存 token
    userStore.setToken(res.data.token);
    
    // 获取用户信息
    await userStore.getUserInfo();
    
    // 跳转到首页
    uni.switchTab({ url: '/pages/index/index' });
  } catch (error) {
    console.error('登录失败：', error);
  }
};
```

### 2. 登出流程

```typescript
import { useUserStore } from '../store/modules/user.store';

const userStore = useUserStore();

const logout = () => {
  // 清除 token 和用户信息
  userStore.logout();
  
  // 跳转到登录页
  uni.redirectTo({ url: '/pages/login/index' });
};
```

### 3. 权限控制

可以使用全局路由守卫或页面级权限检查来实现权限控制：

```typescript
// 在页面 onLoad 中检查权限
import { onLoad } from '@dcloudio/uni-app';
import { useUserStore } from '../store/modules/user.store';

const userStore = useUserStore();

onLoad(() => {
  // 检查是否登录
  if (!userStore.token) {
    uni.redirectTo({ url: '/pages/login/index' });
    return;
  }
  
  // 检查用户权限
  if (!userStore.hasPermission('required_permission')) {
    uni.showToast({
      title: '权限不足',
      icon: 'none'
    });
    uni.navigateBack();
  }
});
```

## 🎨UI 组件

### 1. 使用 Wot Design Uni

FastApp 使用 **Wot Design Uni** 作为 UI 组件库，提供了丰富的移动端组件：

```vue
<template>
  <view class="page">
    <!-- 按钮 -->
    <wd-button type="primary" @click="handleClick">主要按钮</wd-button>
    
    <!-- 输入框 -->
    <wd-input v-model="value" placeholder="请输入内容" />
    
    <!-- 列表 -->
    <wd-list>
      <wd-list-item title="标题" value="值" />
      <wd-list-item title="标题2" value="值2" />
    </wd-list>
    
    <!-- 弹窗 -->
    <wd-popup v-model:visible="popupVisible" title="弹窗标题">
      <view>弹窗内容</view>
    </wd-popup>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const value = ref('');
const popupVisible = ref(false);

const handleClick = () => {
  popupVisible.value = true;
};
</script>
```

### 2. 自定义组件

可以在 `src/components` 目录下创建自定义组件：

```vue
<!-- src/components/custom-button.vue -->
<template>
  <view class="custom-button" @click="$emit('click')">
    <slot></slot>
  </view>
</template>

<script setup lang="ts">
defineEmits(['click']);
</script>

<style scoped>
.custom-button {
  padding: 12rpx 24rpx;
  background-color: #007aff;
  color: #fff;
  border-radius: 8rpx;
  text-align: center;
}
</style>
```

## 📱多平台适配

### 1. 条件编译

使用 Uni App 的条件编译语法，可以为不同平台编写不同的代码：

```vue
<template>
  <view>
    <!-- #ifdef H5 -->
    <view>这是 H5 平台的内容</view>
    <!-- #endif -->
    
    <!-- #ifdef MP-WEIXIN -->
    <view>这是微信小程序平台的内容</view>
    <!-- #endif -->
    
    <!-- #ifdef APP-PLUS -->
    <view>这是 App 平台的内容</view>
    <!-- #endif -->
  </view>
</template>

<script setup lang="ts">
// #ifdef H5
console.log('H5 平台');
// #endif

// #ifdef MP-WEIXIN
console.log('微信小程序平台');
// #endif
</script>

<style scoped>
/* #ifdef H5 */
.view {
  font-size: 16px;
}
/* #endif */

/* #ifdef MP-WEIXIN */
.view {
  font-size: 28rpx;
}
/* #endif */
</style>
```

### 2. 平台特有 API

使用平台特有 API 时，需要注意添加条件编译：

```typescript
// 调用微信小程序特有 API
// #ifdef MP-WEIXIN
wx.getLocation({
  type: 'wgs84',
  success: (res) => {
    console.log('位置信息：', res);
  }
});
// #endif

// 调用 App 特有 API
// #ifdef APP-PLUS
plus.device.getInfo({
  success: (info) => {
    console.log('设备信息：', info);
  }
});
// #endif
```

## 🚀性能优化

### 1. 代码优化

- **减少页面层级**：尽量减少页面嵌套层级，最多不超过 5 层
- **按需加载**：使用分包加载、组件按需导入等方式减少初始包大小
- **避免频繁更新**：使用 `nextTick` 合并更新，避免频繁触发渲染
- **使用虚拟列表**：长列表使用虚拟列表，避免一次性渲染过多数据

### 2. 网络优化

- **缓存数据**：使用本地存储缓存不常变化的数据
- **请求合并**：合并多个请求，减少网络请求次数
- **延迟加载**：非关键资源延迟加载
- **使用 WebSocket**：实时数据使用 WebSocket，减少轮询

### 3. 存储优化

- **合理使用本地存储**：根据数据类型选择合适的存储方式（localStorage、sessionStorage、IndexedDB）
- **清理过期数据**：定期清理过期或无用的数据
- **加密敏感数据**：敏感数据（如 token）进行加密存储

## 📦打包发布

### 1. 构建生产版本

```sh
# 构建 H5 生产版本
pnpm run build:h5

# 构建微信小程序生产版本
pnpm run build:mp-weixin

# 构建其他平台生产版本
pnpm run build:mp-alipay
pnpm run build:mp-baidu
pnpm run build:mp-toutiao
pnpm run build:mp-qq
```

### 2. 发布流程

#### H5 发布

1. 将 `dist/build/h5` 目录部署到静态网站服务器
2. 配置域名、HTTPS 等

#### 微信小程序发布

1. 在微信开发者工具中导入 `dist/build/mp-weixin` 目录
2. 点击「上传」按钮，填写版本号和更新日志
3. 在微信公众平台（mp.weixin.qq.com）提交审核
4. 审核通过后发布上线

#### 其他平台发布

参考各平台官方文档的发布流程。

## 🐛常见问题及解决方案

### 1. 开发环境问题

**问题**：H5 开发时跨域错误
**解决方案**：在 `vite.config.ts` 中配置代理：

```typescript
// vite.config.ts
export default defineConfig({
  server: {
    proxy: {
      '/api': {
        target: 'http://localhost:8001',
        changeOrigin: true
      }
    }
  }
});
```

**问题**：微信小程序开发时 API 请求失败
**解决方案**：在微信公众平台设置合法域名，或在开发者工具中开启「不校验合法域名」选项。

### 2. 运行时问题

**问题**：页面白屏
**解决方案**：检查是否有语法错误、API 调用错误，查看控制台日志。

**问题**：数据加载失败
**解决方案**：检查网络连接，API 地址是否正确，后端服务是否正常。

**问题**：样式错乱
**解决方案**：检查样式代码，使用条件编译适配不同平台。

### 3. 发布问题

**问题**：微信小程序审核失败
**解决方案**：根据审核反馈修改代码，确保符合微信小程序规范。

**问题**：包大小超过限制
**解决方案**：使用分包加载、按需导入组件、压缩资源等方式减少包大小。

## 📚参考文档

- **Uni App 官方文档**：[https://uniapp.dcloud.io/](https://uniapp.dcloud.io/)
- **Wot Design Uni 文档**：[https://wot-design-uni.webapp.plus/](https://wot-design-uni.webapp.plus/)
- **Vue3 官方文档**：[https://v3.vuejs.org/](https://v3.vuejs.org/)
- **TypeScript 官方文档**：[https://www.typescriptlang.org/](https://www.typescriptlang.org/)
- **微信小程序开发文档**：[https://developers.weixin.qq.com/miniprogram/dev/framework/](https://developers.weixin.qq.com/miniprogram/dev/framework/)

## 🤝贡献指南

欢迎为 FastApp 项目贡献代码和建议：

1. **提交 Issue**：报告 bug 或提出新功能建议
2. **提交 Pull Request**：修复 bug 或实现新功能
3. **改进文档**：完善开发文档和使用指南

## 📄许可协议

FastApp 项目采用 MIT 许可协议，详见 [LICENSE](https://github.com/fastapiadmin/FastApp/blob/master/LICENSE) 文件。
