# Personal-web · foxai

> foxai 个人工作站主仓库 —— 站点源码托管 + Cloudflare Pages 部署配置

---

## 📂 仓库结构

```
personal/
├── README.md           # 本文件(项目总览)
├── site/               # Cloudflare Pages 部署源(全部静态资源)
│   ├── index.html
│   ├── favicon.svg
│   ├── README.md
│   └── assets/
└── .gitignore          # 忽略开发期截图/调试脚本/原始素材
```

> Cloudflare Pages 构建配置:
> - **Build command**:`(留空)`
> - **Build output directory**:`site`

---

## 🌐 在线访问

主站入口部署在 Cloudflare Pages,所有业务详情见 [`site/README.md`](site/README.md)。

---

## 🚀 快速部署

### 1. 创建 GitHub 仓库

在 GitHub 新建一个空仓库(建议命名 `Personal-web`),**不要**初始化任何文件(README、license 等全部留空)。

### 2. 推送本地仓库

```bash
cd /path/to/personal
git init
git add .
git commit -m "feat: initial commit · foxai 个人主页"
git branch -M main
git remote add origin https://github.com/<your-username>/Personal-web.git
git push -u origin main
```

### 3. 在 Cloudflare Pages 关联

`Workers & Pages → Create → Pages → Connect to Git`
- 选中刚推送的 `Personal-web` 仓库
- **Build command**:留空
- **Build output directory**:`site`
- 保存后自动部署

---

## 📺 个人案例: mytv 在线影视平台

> 独立设计并开发的在线观影平台:聚合电影、剧集、综艺、动漫资源,支持分类检索、多线路播放与移动端响应式适配,已部署上线稳定运行。

- 🔗 在线访问:**https://tv.19900830.xyz**
- 💻 源码仓库:**https://github.com/LisaPullman/mytv**

---

## 📱 移动端适配

站点已完整适配移动端,关键断点 `900 / 860 / 760 / 720 / 480 px`。`case-media` 在堆叠视图下使用 `aspect-ratio: 16 / 9` 保证案例封面比例稳定。详见 `site/README.md`。

---

## 📫 联系

- 邮箱:**foxbobby@qq.com**
- 部署:**Cloudflare Pages**

---

© 2026 foxai · 创造者 · 全栈交付