# MarkLumen

## 项目描述
一个优雅的Markdown文章展示平台，以精美博客形式展示数据库/本地存储中的Markdown文件。提供划线交互、自动推荐等增强功能，提升阅读体验。

## 核心功能
- 📝 精美博客式Markdown文章展示
- 🎯 文本划线标记与高亮
- 💡 智能划线内容推荐
- 🏷️ 标签分类与搜索
- 💾 本地Markdown文件存储与管理

## 前端技术栈

### 核心框架
- **React 18** - UI组件库
- **React Router v6** - 路由管理
- **TypeScript** - 类型安全

### UI & 样式
- **Tailwind CSS** - 工具类样式框架
- **React Markdown** - Markdown渲染引擎
- **Highlight.js** - 代码高亮
- **React Icons** - 图标库

### 状态管理 & 数据
- **Zustand** - 轻量级状态管理
- **React Query** - 数据获取与缓存

### 开发工具
- **Vite** - 前端构建工具
- **ESLint & Prettier** - 代码规范

## 架构设计

### 分层架构

```
┌─────────────────────────────────────┐
│       Presentation Layer (UI)       │
│  (Pages, Components, Hooks)         │
└────────────┬────────────────────────┘
             │
┌────────────▼────────────────────────┐
│       Service Layer (业务逻辑)       │
│  (MarkdownService, Utils)           │
└────────────┬────────────────────────┘
             │
┌────────────▼────────────────────────┐
│       Data Layer (数据获取)          │
│  (Local Storage, API Client)        │
└─────────────────────────────────────┘
```

### 核心Service设计

**MarkdownService** - 封装Markdown文件获取逻辑
- `getAllArticles()` - 获取所有文章列表
- `getArticleById(id)` - 获取单篇文章
- `searchArticles(keyword)` - 搜索文章
- `addHighlight(articleId, highlight)` - 保存划线
- `getHighlights(articleId)` - 获取文章划线

## 项目结构

```
MarkLumen/
├── public/
├── src/
│   ├── components/          # 可复用组件
│   │   ├── ArticleCard.tsx
│   │   ├── MarkdownViewer.tsx
│   │   ├── HighlightBar.tsx
│   │   └── SearchBar.tsx
│   ├── pages/              # 页面组件
│   │   ├── ArticleList.tsx
│   │   ├── ArticleDetail.tsx
│   │   └── NotFound.tsx
│   ├── services/           # 业务逻辑层
│   │   ├── markdownService.ts
│   │   └── storageService.ts
│   ├── stores/             # 状态管理
│   │   └── articleStore.ts
│   ├── types/              # TypeScript类型定义
│   │   └── article.ts
│   ├── utils/              # 工具函数
│   │   └── highlighter.ts
│   ├── App.tsx
│   └── main.tsx
├── articles/               # 本地Markdown测试文件存储目录
│   ├── article1.md
│   ├── article2.md
│   └── ...
├── package.json
├── vite.config.ts
└── tsconfig.json
```

## 快速开始

### 安装依赖
```bash
cd markdown-reader-app
npm install
npm install react-router-dom
npm install react-markdown remark-gfm rehype-raw rehype-sanitize
npm install highlight.js
npm install react-icons
```

### 安装开发依赖
```bash
# 仅仅是开发者工具
npm install -D tailwindcss postcss autoprefixer
npm install -D @types/react-router-dom
```
#### 初始化Taiwind CSS
```
npx tailwindcss init -p
```

### 启动开发服务器
```bash
npm run dev
```

### 构建生产版本
```bash
npm run build
```

## 使用说明

### 添加Markdown文章
1. 在 `articles/` 目录下创建 `.md` 文件
2. 文件自动被扫描并展示在首页列表中
3. 点击文章卡片进入详情页

### 划线功能
- 在文章内选中文本，点击高亮按钮进行划线
- 划线内容自动保存到本地存储
- 支持删除和编辑划线备注

### 未来扩展方向
- [ ] 后端API集成（替换本地存储）
- [ ] 用户账号系统
- [ ] 评论与讨论功能
- [ ] AI驱动的内容推荐
- [ ] 导出与分享功能
