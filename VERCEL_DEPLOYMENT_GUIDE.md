# Vercel 部署指南

## 前提条件

1. 确保代码已成功推送到GitHub仓库：https://github.com/yhai3596/ai-tool
2. 拥有Vercel账号（如果没有，请访问 https://vercel.com 注册）

## 步骤1：连接GitHub到Vercel

1. 访问 [Vercel Dashboard](https://vercel.com/dashboard)
2. 点击 "New Project"
3. 选择 "Import Git Repository"
4. 如果首次使用，需要连接GitHub账号：
   - 点击 "Continue with GitHub"
   - 授权Vercel访问你的GitHub账号

## 步骤2：导入项目

1. 在项目列表中找到 `yhai3596/ai-tool`
2. 点击 "Import"
3. 配置项目设置：
   - **Project Name**: `aiverse` 或 `ai-tool-directory`
   - **Framework Preset**: Vite
   - **Root Directory**: `./` (保持默认)
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`

## 步骤3：配置环境变量

在部署配置页面，添加以下环境变量：

### 必需的环境变量：
```
VITE_SUPABASE_URL=你的Supabase项目URL
VITE_SUPABASE_ANON_KEY=你的Supabase匿名密钥
```

### 可选的环境变量：
```
VITE_GA_TRACKING_ID=你的Google Analytics ID
VITE_HOTJAR_ID=你的Hotjar ID
VITE_SENTRY_DSN=你的Sentry DSN
VITE_BUILD_MODE=production
```

### 获取Supabase配置：
1. 访问 [Supabase Dashboard](https://supabase.com/dashboard)
2. 选择你的项目
3. 进入 Settings > API
4. 复制 "Project URL" 和 "anon public" 密钥

## 步骤4：部署

1. 确认所有配置正确
2. 点击 "Deploy"
3. 等待部署完成（通常需要2-5分钟）

## 步骤5：验证部署

部署完成后：

1. 访问Vercel提供的部署URL
2. 检查以下功能：
   - 页面正常加载
   - AI工具列表显示
   - 搜索功能工作
   - 分类筛选功能
   - 响应式设计在移动设备上正常

## 步骤6：配置自定义域名（可选）

1. 在Vercel项目设置中，进入 "Domains"
2. 添加你的自定义域名
3. 按照Vercel的指引配置DNS记录

## 常见问题解决

### 构建失败
- 检查 `package.json` 中的依赖是否正确
- 确保构建命令是 `npm run build`
- 检查是否有TypeScript错误

### 环境变量问题
- 确保所有 `VITE_` 前缀的环境变量都已设置
- 重新部署以应用新的环境变量

### Supabase连接问题
- 验证Supabase URL和密钥是否正确
- 检查Supabase项目是否处于活跃状态

## 部署后的优化

1. **性能监控**: 在Vercel Analytics中监控网站性能
2. **SEO优化**: 确保meta标签和Open Graph标签正确设置
3. **错误监控**: 配置Sentry进行错误追踪
4. **分析工具**: 设置Google Analytics追踪用户行为

## 自动部署

配置完成后，每次向GitHub主分支推送代码时，Vercel会自动重新部署网站。

## 联系支持

如果遇到问题：
1. 查看Vercel部署日志
2. 检查浏览器控制台错误
3. 参考Vercel官方文档：https://vercel.com/docs