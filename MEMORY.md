# MEMORY.md

## 项目：citeglow.com 网站部署

### 用户
- GitHub: DMing1001
- 域名: citeglow.com（Vercel 部署）
- 公众号: 题序羊 | 微信: Sheep_TD | QQ: 1591048061

### 架构
- **Citation-tracker 仓库** → citeglow.com/（Vercel 托管主站）
- **water-teaching 仓库** → 源仓库，用户在此开发
- **Citation-tracker/water-teaching/** → citeglow.com/water-teaching/（子页面部署路径）

### 同步规则
water-teaching 仓库更新 → 用户确认 → 同步到 Citation-tracker/water-teaching/ → Vercel 自动部署

### 备注
- Git HTTPS 推送在该服务器不稳定，可用 GitHub API 替代
- water-teaching 页面：HEC-RAS & ArcGIS Pro 水利教学，深色单页
- 不加"返回主站"按钮，water-teaching 作为独立页面
