# MkDocs + Material + GitHub Actions 部署方案

## 🎉 部署完成！

您的财经分析报告系统已成功配置为使用 MkDocs + Material 主题，并通过 GitHub Actions 自动部署。

## 📋 已完成的工作

### ✅ 1. MkDocs 配置
- 创建了 `mkdocs.yml` 配置文件
- 配置了 Material 主题
- 设置了中文语言支持
- 配置了深色/浅色模式切换

### ✅ 2. 文档结构
- 创建了 `docs/` 目录
- 移动了所有文档文件到 `docs/` 目录
- 创建了专业的首页 `index.md`
- 保留了原有的分析报告结构

### ✅ 3. 自动导航生成
- 创建了 `scripts/generate_mkdocs_nav.py` 脚本
- 自动扫描 `archive` 目录结构
- 按月份和日期组织导航菜单
- 支持动态更新导航配置

### ✅ 4. GitHub Actions 部署
- 创建了 `.github/workflows/deploy-mkdocs.yml` 工作流
- 配置了自动构建和部署
- 支持推送到 main 分支自动部署
- 支持 PR 预览功能

### ✅ 5. 辅助工具
- 创建了 `requirements.txt` 依赖文件
- 创建了 `scripts/deploy.sh` 部署脚本
- 创建了详细的部署文档

## 🚀 使用方法

### 本地开发
```bash
# 安装依赖
pip install -r requirements.txt

# 启动开发服务器
mkdocs serve

# 访问 http://127.0.0.1:8000
```

### 自动部署
```bash
# 生成导航并构建
./scripts/deploy.sh

# 推送到 GitHub 自动部署
git add .
git commit -m "更新文档"
git push origin main
```

### 手动更新导航
```bash
# 自动生成导航配置
python3 scripts/generate_mkdocs_nav.py
```

## 🌟 主要特性

### 🎨 美观的界面
- **Material Design**：现代化的设计风格
- **响应式布局**：支持桌面和移动设备
- **主题切换**：深色/浅色模式自动切换
- **中文支持**：完整的中文界面

### 📊 智能导航
- **自动生成**：根据文件结构自动生成导航
- **层级清晰**：按月份→日期→文件组织
- **动态更新**：新增报告自动更新导航

### 🔍 强大功能
- **全文搜索**：支持中文搜索
- **代码高亮**：支持多种编程语言
- **表格支持**：美观的表格显示
- **链接检查**：自动检查链接有效性

### 🚀 自动化部署
- **GitHub Actions**：自动构建和部署
- **GitHub Pages**：免费托管静态网站
- **PR 预览**：支持 Pull Request 预览
- **版本控制**：完整的版本历史

## 📁 项目结构

```
Financial-report/
├── mkdocs.yml                    # MkDocs 配置
├── requirements.txt              # Python 依赖
├── docs/                         # 文档源文件
│   ├── index.md                 # 首页
│   ├── README.md                # 项目说明
│   ├── DEPLOYMENT.md            # 部署指南
│   ├── archive/                 # 分析报告存档
│   └── prompts/                 # 提示词配置
├── .github/workflows/           # GitHub Actions
│   └── deploy-mkdocs.yml       # 部署工作流
├── scripts/                     # 辅助脚本
│   ├── generate_mkdocs_nav.py  # 导航生成
│   └── deploy.sh               # 部署脚本
└── site/                        # 构建输出（自动生成）
```

## 🔧 配置说明

### 更新仓库信息
在 `mkdocs.yml` 中更新以下配置：

```yaml
site_url: https://your-username.github.io/Financial-report
repo_name: your-username/Financial-report
repo_url: https://github.com/your-username/Financial-report
```

### 自定义主题
```yaml
theme:
  name: material
  language: zh
  palette:
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: blue
      accent: blue
```

## 📝 下一步

1. **更新仓库信息**：在 `mkdocs.yml` 中更新您的 GitHub 用户名
2. **推送代码**：将代码推送到 GitHub 仓库
3. **启用 Pages**：在仓库设置中启用 GitHub Pages
4. **访问网站**：访问 `https://your-username.github.io/Financial-report`

## 🆘 故障排除

### 常见问题
- **构建失败**：检查 `mkdocs.yml` 语法
- **页面404**：确认文件路径正确
- **导航不显示**：运行 `python3 scripts/generate_mkdocs_nav.py`
- **样式问题**：检查 Material 主题配置

### 调试命令
```bash
# 详细构建信息
mkdocs build --verbose

# 检查配置
mkdocs config

# 清理构建目录
rm -rf site/
```

## 🎯 优势对比

| 特性 | 原方案 | MkDocs + Material |
|------|--------|-------------------|
| 界面美观 | ❌ 基础 | ✅ 现代化 |
| 响应式设计 | ❌ 不支持 | ✅ 完全支持 |
| 搜索功能 | ❌ 无 | ✅ 全文搜索 |
| 主题切换 | ❌ 无 | ✅ 深色/浅色 |
| 自动部署 | ❌ 手动 | ✅ 全自动 |
| 维护成本 | ❌ 高 | ✅ 低 |

## 📞 技术支持

如有问题，请参考：
- [部署文档](docs/DEPLOYMENT.md)
- [MkDocs 官方文档](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

---

**恭喜！您的财经分析报告系统现在拥有了专业级的文档网站！** 🎉
