# foxai 个人主页 · site/

> foxai · 创造者 · 全栈交付 — 个人工作站源码
> 在线访问:https://foxai.pages.dev(部署在 Cloudflare Pages)

纯静态单页站点,零构建、零依赖,所有 CSS/JS 内联在 `index.html` 中,可直接拖拽到 Cloudflare Pages。

---

## 📺 个人案例

### 案例一 · mytv · 在线影视平台(独立全栈交付)

> 独立设计并开发的在线观影平台:聚合电影、剧集、综艺、动漫资源,支持分类检索、多线路播放与移动端响应式适配,已部署上线稳定运行。

- 🔗 在线访问:**https://tv.19900830.xyz**
- 💻 源码仓库:**https://github.com/LisaPullman/mytv**
- 🛠 技术栈:Web 应用 · 全流程自研
- ☁️ 部署环境:Cloudflare Pages
- 📱 响应式:已适配桌面 / 移动端

### 案例二 · Text2img · AI 文生图(Cloudflare Workers 边缘应用)

> 基于 Cloudflare Workers AI 的免费文生图服务:内置 FLUX schnell 等 9 个模型,支持比例预设、批量生成与深浅色模式,无需服务器、全球边缘加速,开箱即用。

- 🔗 在线访问:**https://pic.foxai.edu.kg/**
- 💻 源码仓库:**https://github.com/LisaPullman/foxai-Text2img-Cloudflare-Workers**
- 🛠 技术栈:Cloudflare Workers AI · Serverless 边缘部署
- ☁️ 部署环境:Cloudflare Workers
- 📱 响应式:已适配桌面 / 移动端

> 版式说明:两个案例在桌面端(>900px)交错排布——案例一媒体在左,案例二(`.case.flip`)媒体在右;≤900px 统一恢复为「上图下文」单列。

---

## 📱 移动端适配

站点已完整适配移动端,关键断点:

| 断点 | 行为 |
| --- | --- |
| ≤ 900px | hero / case 切换为单列堆叠 |
| ≤ 860px | services / process 切换为单列 |
| ≤ 760px | 导航菜单折叠,仅保留 logo + 联系入口 |
| ≤ 720px | 品牌总览图切换为竖版(`board-portrait.png`) |
| ≤ 480px | 全局边距、字号、按钮进一步收紧 |

`case-media` 在移动端使用 `aspect-ratio: 16 / 9`,保证案例封面在堆叠视图中比例稳定。

---

## 📂 目录结构

```
site/
├── index.html                 # 页面(全部 CSS / JS 内联)
├── favicon.svg                # foxai「Trace」标志 · Tile 版
├── README.md                  # 本文件
└── assets/
    ├── board-landscape.png    # 品牌总览图(横版 / 桌面端)
    ├── board-portrait.png     # 品牌总览图(竖版 / 移动端)
    ├── id-card.png            # GEEK ID 2049 证件卡
    ├── case-mytv.png          # mytv 项目封面(源图为 电影电视.png)
    └── case-flux.png          # Text2img 项目封面(源图为 FLUX schnell.png)
```

---

## 🚀 部署到 Cloudflare Pages

### 方式一:网页拖拽(最简单 · 约 1 分钟)

1. 打开 https://dash.cloudflare.com → 左侧 **Workers & Pages** → **Create** → **Pages** 标签
2. 选择 **Upload assets(直接上传)**
3. 项目名随意(如 `foxai`),把整个 `site/` 文件夹拖入
4. 点击 **Deploy**,完成后即可访问 `https://<项目名>.pages.dev`

### 方式二:wrangler CLI

```bash
npm install -g wrangler
wrangler login
wrangler pages deploy . --project-name=foxai
```

> 在 `site/` 目录内执行上述命令。

### 方式三:连接 Git 仓库

`Pages → Create → Connect to Git` 选中仓库后:

- **Build command**:留空
- **Build output directory**:填 `site`
- 每次 push 自动触发部署

---

## 💻 本地预览

```bash
cd site
python3 -m http.server 8799
# 浏览器打开 http://localhost:8799
```

或使用任意静态服务器(无需构建步骤):

```bash
npx serve site
```

---

## ✏️ 修改指引

| 想改什么 | 位置 |
| --- | --- |
| 联系邮箱 | 全局替换 `foxbobby@qq.com`(共 7 处,含 nav / hero / contact / JSON-LD) |
| 品牌主色 | `index.html` 顶部 `:root` 中的 `--brand`(当前 `#FF7A4D`,foxai Ember 暗色版) |
| 业务文案 | `#services` 区块内四张卡片 |
| 流程文案 | `#process` 区块 |
| 案例区块 | `#work`,数据(简介、链接、Chips)在 `index.html` 第 ~562 行附近 |
| 联系方式 | `#contact` 区块 + nav / hero 中的 `mailto:` 链接 |

---

## 📄 License

© 2026 foxai · deployed on Cloudflare Pages