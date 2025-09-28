# AIverse 项目部署指南

## 📋 部署前准备

### 1. 项目准备
- ✅ 项目已配置好 `vercel.json`
- ✅ 构建脚本已优化
- ✅ 环境变量配置已准备
- ✅ 本地构建测试通过

### 2. 所需账户
- GitHub 账户
- Vercel 账户
- Supabase 账户（如果需要独立的生产环境）

## 🚀 GitHub 部署步骤

### 步骤 1: 推送代码到 GitHub

1. **初始化 Git 仓库**（如果还没有）
   ```bash
   git init
   git add .
   git commit -m "Initial commit: AIverse project ready for deployment"
   ```

2. **创建 GitHub 仓库**
   - 登录 GitHub
   - 点击 "New repository"
   - 仓库名称：`aiverse`
   - 设置为 Public 或 Private
   - 不要初始化 README（因为本地已有）

3. **连接并推送到 GitHub**
   ```bash
   git remote add origin https://github.com/你的用户名/aiverse.git
   git branch -M main
   git push -u origin main
   ```

### 步骤 2: 在 Vercel 上部署

1. **登录 Vercel**
   - 访问 [vercel.com](https://vercel.com)
   - 使用 GitHub 账户登录

2. **导入项目**
   - 点击 "New Project"
   - 选择你的 GitHub 仓库 `aiverse`
   - 点击 "Import"

3. **配置项目设置**
   - **Framework Preset**: Vite
   - **Root Directory**: `./` (根目录)
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`

4. **配置环境变量**
   在 Vercel 项目设置中添加以下环境变量：
   ```
   VITE_SUPABASE_URL=https://ncfqyasvfvrtpoaqfegl.supabase.co
   VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im5jZnF5YXN2ZnZydHBvYXFmZWdsIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NTU3NDk5ODQsImV4cCI6MjA3MTMyNTk4NH0.BBrmj8rvbWCOtnxQOVrRgG_gGQvSPDhyVtIMuD5CjIo
   ```

5. **部署**
   - 点击 "Deploy"
   - 等待构建完成（通常需要 2-5 分钟）

## 🔧 高级配置

### 自定义域名
1. 在 Vercel 项目设置中点击 "Domains"
2. 添加你的自定义域名
3. 按照提示配置 DNS 记录

### 环境变量管理
- **开发环境**: 使用 `.env.local`
- **生产环境**: 在 Vercel 控制台配置
- **预览环境**: 可以设置不同的环境变量

### 性能优化
项目已包含以下优化：
- 静态资源缓存（1年）
- 安全头设置
- SPA 路由重写
- 代码分割警告

## 🔍 部署后验证

### 1. 功能测试
- [ ] 首页加载正常
- [ ] 搜索功能工作
- [ ] 工具卡片显示正确
- [ ] 路由导航正常
- [ ] 响应式设计正常

### 2. 性能检查
- [ ] 页面加载速度 < 3秒
- [ ] Lighthouse 分数 > 90
- [ ] 移动端体验良好

### 3. SEO 验证
- [ ] Meta 标签正确
- [ ] Open Graph 标签正常
- [ ] 结构化数据正确

## 🐛 常见问题解决

### 构建失败
```bash
# 本地测试构建
npm run build

# 检查依赖
npm install
```

### 环境变量问题
- 确保所有 `VITE_` 前缀的变量都在 Vercel 中配置
- 检查变量名拼写是否正确

### 路由 404 错误
- 确保 `vercel.json` 中的重写规则正确
- 检查 React Router 配置

### Supabase 连接问题
- 验证 Supabase URL 和 API Key
- 检查 Supabase 项目状态
- 确认数据库表结构正确

## 📊 监控和维护

### 1. Vercel Analytics
- 在项目设置中启用 Analytics
- 监控页面性能和用户行为

### 2. 错误监控
- 考虑集成 Sentry 或其他错误监控服务
- 设置错误告警

### 3. 定期更新
- 定期更新依赖包
- 监控安全漏洞
- 备份数据库

## 🎯 部署成功！

部署完成后，你的 AIverse 项目将在以下地址可用：
- **Vercel 默认域名**: `https://aiverse-你的用户名.vercel.app`
- **自定义域名**: 如果配置了自定义域名

享受你的 AI 工具目录平台吧！🚀