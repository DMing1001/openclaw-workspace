# MEMORY.md

## 用户信息
- **GitHub**: DMing1001
- **域名**: citeglow.com（Vercel 部署）
- **微信公众号**: 题序羊
- **微信**: Sheep_TD
- **QQ**: 1591048061
- **邮箱**: Minghao_xut1011@outlook.com

---

## GitHub 仓库总览

### 1. Citation-tracker — 论文引用追踪器
- **仓库**: DMing1001/Citation-tracker
- **地址**: citeglow.com/（Vercel 部署到根域名）
- **功能**: 输入论文 DOI，自动获取引用数，统一管理论文引用情况
- **技术栈**: 纯前端单页应用（HTML + CSS + JS），数据存 localStorage
- **结构**: index.html + journals/ 目录（期刊数据）
- **部署**: Vercel 连接此仓库，根目录即主站

### 2. water-teaching — 水利数值模拟教学
- **仓库**: DMing1001/water-teaching（源仓库）
- **地址**: citeglow.com/water-teaching/（通过 Citation-tracker/water-teaching/ 子目录部署）
- **功能**: HEC-RAS & ArcGIS Pro 教学页面，含视频链接、PDF 手册下载、联系方式
- **技术栈**: 纯前端单页应用，深色主题
- **结构**: index.html + docs/（PDF 参考手册）
- **联系**: Bilibili / 邮箱 / 公众号「题序羊」/ 微信 Sheep_TD / QQ 1591048061

#### ⚠️ 同步规则（重要）
1. 用户先在 `DMing1001/water-teaching` 仓库更新内容
2. 用户确认无误后，通知我同步
3. 我将内容同步到 `DMing1001/Citation-tracker/water-teaching/`
4. Vercel 自动部署到 citeglow.com/water-teaching/
5. **两个仓库必须保持一致**，water-teaching 是源仓库，Citation-tracker/water-teaching/ 是部署目录

### 2.5 Citation-tracker 期刊投稿指南（持续更新）
- **位置**: Citation-tracker/journals/ 目录
- **内容**: 各期刊独立 HTML 页面（如 agricultural-water-management.html、catena.html 等）
- **共享资源**: feedback.css、feedback.js 等
- **更新方式**: 直接在 Citation-tracker 仓库操作，push 即部署到 citeglow.com/journals/

---

## 🗣️ 对话速查（用户怎么说，我怎么做）

| 用户说 | 我做 |
|---|---|
| "water-teaching 更新好了，同步到 citeglow" | 从 DMing1001/water-teaching 拉取 → 放入 Citation-tracker/water-teaching/ → 部署 |
| "加一个期刊 xxx 的投稿指南" | 在 Citation-tracker/journals/ 新增 HTML 页面 |
| "改一下 xxx 期刊的投稿指南" | 修改 Citation-tracker/journals/xxx.html |
| Citation-tracker 主站（index.html）| 一般不动，已经够用 |

### 3. sci-tracker — SCI 投稿追踪面板
- **仓库**: DMing1001/sci-tracker
- **功能**: 一站式管理多篇 SCI 论文投稿进度
- **技术栈**: 纯前端单页应用（HTML + CSS + JS），数据存 localStorage
- **核心特性**:
  - 自动同步：粘贴 Elsevier AuthorHub 追踪链接，自动获取稿件信息
  - 手动管理：支持非 Elsevier 期刊手动录入
  - 中英切换、深色/浅色主题
  - 筛选排序、展开详情、数据导出（JSON）
  - 批量同步所有 Elsevier 投稿
- **外部 API**: Elsevier AuthorHub 公开端点（`https://tnlkuelk67.execute-api.us-east-1.amazonaws.com/tracker/{uuid}`）
- **设计**: 状态标签始终用英文，日期格式按语言切换

### 4. sticky-notes（墨滴 Modī）— 桌面便笺应用
- **仓库**: DMing1001/sticky-notes
- **功能**: 基于 Electron 的轻量桌面便笺
- **技术栈**: Electron + 单文件 HTML（main.js + index.html + preload.js）
- **特色功能**:
  - 多便笺、拖拽/缩放、8 种配色、深浅主题
  - 搜索（含高亮）、网格排列（Masonry 瀑布流）
  - 置顶、折叠、复制、Checklist 模式
  - 暖心消息（8 个时段 × 10 句话）
  - 系统托盘常驻、全局快捷键 Ctrl+Shift+N
  - 单实例锁定、JSON 导入/导出
  - Markdown 快捷输入（`- `、`* `、`# `、`> `）
- **CI/CD**: GitHub Actions
  - push main → 自动部署 GitHub Pages
  - 打 tag（如 v1.0.0）→ 自动构建 Electron exe → GitHub Release
- **构建**: `npm run build:win`（本地）/ `npx electron-builder --win --publish never`（CI）

### 5. openclaw-workspace — OpenClaw 记忆仓库
- **仓库**: DMing1001/openclaw-workspace
- **功能**: 存储 OpenClaw agent 的记忆和配置文件
- **包含**: MEMORY.md, memory/*.md, AGENTS.md, SOUL.md, USER.md 等

---

## 技术备注
- Git HTTPS 推送在当前服务器不稳定，可用 GitHub API 直接更新文件作为替代
- GitHub Token 已提供（注意用完安全）
- citeglow.com 由 Vercel 托管，push 到 Citation-tracker 仓库即自动部署
