# Life Graph App

## 项目简介

**Life Graph App** 是一个基于跨平台前端技术构建的生活记忆与关系图谱应用。它能够帮助用户以节点和网络的形式，直观地记录和回忆生活中的重要瞬间和社交联系。应用注重用户隐私保护，所有数据（如文本、图片及音频）均优先存储在本地数据库（如 SQLite）。

## 技术栈

- **核心框架**: Vue 3
- **状态管理**: Pinia
- **路由管理**: Vue Router
- **构建工具**: Vite
- **跨平台引擎**: Capacitor (用于构建 iOS 和 Android 应用)
- **开发语言**: TypeScript
- **代码规范与格式化**: ESLint + Prettier

## 分支开发策略

为了保证代码的协同开发和持续交付质量，本项目遵循以下分支模型：

- **`main` 分支**: 保护分支。包含可发布的、经过完全测试的代码。任何时候都不要直接向 `main` 分支提交代码。
- **`dev` 分支**: 保护分支。日常开发的主分支，包含最新的开发阶段代码。
- **`feature/*` 分支**: 功能开发分支。当需要开发新功能 (例如 `feature/login`，`feature/graph-render`) 时，从 `dev` 检出；开发完成后提 PR 合并回 `dev`。

## 项目启动与使用

### 安装依赖

```bash
npm install
```

### 开发环境调试

```bash
npm run dev
```

### 生产环境构建

```bash
npm run build
```

### 代码检查

```bash
npm run type-check  # 运行 TypeScript 类型检查
npm run lint        # 运行代码风格检查 (ESLint)
```
