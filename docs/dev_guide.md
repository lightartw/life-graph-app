# 团队协作开发指南 (Contributing)

## 前置要求 (Prerequisites)

- Git
- Node.js 20+
- npm

## 分支管理与分配策略

- **`main` (生产主分支)**：代表随时可发布的稳定产物。
  - 权限：**禁止任何人直接 Push**。
  - 来源：只能通过 `dev` 分支提 PR 合并进来。

- **`dev` (开发集成分支)**：用于汇总所有人开发成果的“公共测试大厅”。
  - 权限：**禁止任何人直接 Push**。
  - 来源：只能接收大家从自己临时分支提的 PR。

- **`feat/你的名字-功能名` (个人分支)**：这是你私有的一次性开发区。
  - 分配原则：你要写任何功能，必须以最新的 `dev` 为起点，新建一个分支（如 `feat/zhangsan-login`）。写完交 PR 合并后，该分支生命周期完全结束。

## 获取项目 (Clone)

如果你已经克隆过本仓库，请跳过此步。

```bash
git clone https://github.com/<主仓库用户名或组织名>/life-graph-app.git
cd life-graph-app
```

## 更新本地代码并创建分支

准备写新功能前，必须拉取最新成果，避免后续冲突！

```bash
git fetch --all
git checkout dev
git pull origin dev
```

创建你的个人专用分支

```bash
git checkout -b <你的分支名>
```

_(命名建议：`feat/功能名` 或 `fix/bug名`)_

## 安装依赖

```bash
npm ci
```

## 启动本地开发服务器

运行网页端开发环境：

```bash
npm run dev
```

## 提交代码 (Commit)

提交前，请务必运行代码检查与格式化，拦截格式问题：

```bash
npm run lint
npm run format
```

正式提交：

```bash
git add .
git commit -m "<使用规范的提交信息>"
```

_(参考：`feat: 新增首页图表` / `fix: 修复导航栏闪退`)_

## 推送并创建 PR (Pull Request)

**1. 直接推送到主仓库**

```bash
git push origin <你的分支名> -u
```

**2. 提交申请与清场:**

1. 访问项目的 GitHub 主页面。
2. 转到 **Pull requests** 标签页，点击 **New pull request**。
3. 左侧 Base 选 `dev` ；右侧 Compare 选 `你的分支`。
4. 点击 **Create pull request** 提交审核。
5. 当组长或机器人批准了你的 PR 并合并后，请务必点击网页上的 **Delete branch** 按钮，删除这段临时分支
