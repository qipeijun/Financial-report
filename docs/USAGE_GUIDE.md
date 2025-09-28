# 📖 财经分析报告系统使用说明

## 🎯 系统概述

本系统是一个基于 AI 的财经分析报告生成平台，使用 MkDocs + Material 主题构建专业文档网站，支持自动化部署和智能导航生成。

## 🚀 快速开始

### 1. 环境准备

确保您的系统已安装：
- Python 3.8+
- Git
- 浏览器

### 2. 本地开发

```bash
# 克隆项目
git clone https://github.com/your-username/Financial-report.git
cd Financial-report

# 安装依赖
pip install -r requirements.txt

# 启动开发服务器
mkdocs serve

# 访问 http://127.0.0.1:8000 查看本地预览
```

## 📝 日常使用流程

### 生成新的财经分析报告

#### 方法一：使用 AI 工具（推荐）

1. **准备提示词**：
   - 使用 `docs/prompts/` 目录下的提示词文件
   - 推荐使用 `mcp_finance_analysis_prompt_optimized.md`

2. **创建报告目录**：
   ```
   docs/archive/2025-01/2025-01-15_gemini/
   ├── rss_data/          # RSS 原始数据
   ├── news_content/      # 新闻正文内容
   ├── analysis/          # 分析结果
   └── reports/           # 最终报告
   ```

3. **生成报告文件**：
   - 将 AI 生成的分析结果保存到对应目录
   - 确保报告文件为 `.md` 格式

#### 方法二：手动创建

1. **创建目录结构**：
   ```bash
   mkdir -p docs/archive/2025-01/2025-01-15_gemini/{rss_data,news_content,analysis,reports}
   ```

2. **编写报告**：
   - 在 `reports/` 目录下创建 Markdown 文件
   - 使用标准的财经分析报告格式

### 部署和发布

#### 自动部署（推荐）

1. **提交代码**：
   ```bash
   git add .
   git commit -m "新增 2025-01-15 财经分析报告"
   git push origin main
   ```

2. **自动处理**：
   - GitHub Actions 自动生成导航菜单
   - 自动构建文档网站
   - 自动部署到 GitHub Pages

#### 本地部署

```bash
# 运行部署脚本
./scripts/deploy.sh

# 或手动执行
python3 scripts/generate_mkdocs_nav.py  # 生成导航
mkdocs build                            # 构建文档
```

## 📁 文件结构说明

```
docs/
├── index.md                    # 网站首页
├── index.md                    # 首页
├── DEPLOYMENT.md              # 部署指南
├── prompts/                   # 提示词配置
│   ├── mcp_finance_analysis_prompt.md           # 完整版
│   ├── mcp_finance_analysis_prompt_optimized.md # 优化版
│   └── mcp_finance_analysis_prompt_minimal.md   # 精简版
└── archive/                   # 分析报告存档
    └── YYYY-MM/              # 按月份组织
        └── YYYY-MM-DD_model/ # 按日期和模型组织
            ├── rss_data/     # RSS 原始数据
            ├── news_content/ # 新闻正文内容
            ├── analysis/     # 分析结果
            └── reports/      # 最终报告
```

## 🛠️ 常用命令

### 开发命令

```bash
# 启动开发服务器
mkdocs serve

# 构建静态网站
mkdocs build

# 检查配置
mkdocs config

# 清理构建目录
rm -rf site/
```

### 脚本命令

```bash
# 生成导航菜单
python3 scripts/generate_mkdocs_nav.py

# 一键部署
./scripts/deploy.sh

# 查看帮助
./scripts/deploy.sh --help
```

## 📊 报告格式规范

### 标准报告结构

```markdown
# 📅 2025-01-15 财经分析报告

## 📈 市场概览
- 市场整体表现
- 主要指数变化

## 🔥 热门话题 TOP3
### 1. 话题名称
- **催化剂**：上涨原因
- **复盘**：过去走势分析
- **展望**：未来预期
- **相关股票**：推荐标的

## 💎 潜力话题 TOP3
### 1. 话题名称
- **催化剂**：潜在驱动因素
- **复盘**：历史表现
- **展望**：发展前景
- **相关股票**：投资标的

## 💰 股票推荐
### 强烈推荐
1. 股票名称 (代码) - 推荐理由
2. 股票名称 (代码) - 推荐理由

### 谨慎推荐
1. 股票名称 (代码) - 风险提示

## ⚠️ 风险提示
- 市场风险
- 政策风险
- 其他风险因素

---
*生成时间：2025-01-15 | 数据源：13个RSS*
```

## 🔧 配置说明

### MkDocs 配置

主要配置文件：`mkdocs.yml`

```yaml
site_name: 财经分析报告系统
docs_dir: docs
theme:
  name: material
  language: zh
```

### GitHub Actions 配置

自动部署配置：`.github/workflows/deploy-mkdocs.yml`

- 支持 main 和 master 分支
- 自动生成导航菜单
- 自动构建和部署

## 🎨 自定义配置

### 修改网站信息

编辑 `mkdocs.yml`：

```yaml
site_name: 您的网站名称
site_description: 网站描述
site_author: 作者名称
site_url: https://your-username.github.io/Financial-report
```

### 修改主题颜色

```yaml
theme:
  palette:
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: blue    # 主色调
      accent: blue     # 强调色
```

### 添加新页面

1. 在 `docs/` 目录下创建 Markdown 文件
2. 运行 `python3 scripts/generate_mkdocs_nav.py` 更新导航
3. 或手动编辑 `mkdocs.yml` 中的 `nav` 配置

## 🐛 故障排除

### 常见问题

#### 1. 构建失败

**问题**：`mkdocs build` 失败

**解决方案**：
```bash
# 检查配置
mkdocs config

# 详细构建信息
mkdocs build --verbose

# 检查文件路径
ls -la docs/
```

#### 2. 导航不显示

**问题**：新报告没有出现在导航中

**解决方案**：
```bash
# 重新生成导航
python3 scripts/generate_mkdocs_nav.py

# 检查文件结构
find docs/archive -name "*.md" -type f
```

#### 3. 部署失败

**问题**：GitHub Actions 部署失败

**解决方案**：
1. 检查 GitHub Pages 设置
2. 确认仓库权限
3. 查看 Actions 日志

#### 4. 本地预览问题

**问题**：`mkdocs serve` 无法启动

**解决方案**：
```bash
# 重新安装依赖
pip install -r requirements.txt

# 检查端口占用
lsof -i :8000

# 使用其他端口
mkdocs serve -a 127.0.0.1:8001
```

### 调试命令

```bash
# 检查 Python 环境
python3 --version
pip list | grep mkdocs

# 检查文件权限
ls -la scripts/
chmod +x scripts/deploy.sh

# 查看详细日志
mkdocs build --verbose
```

## 📞 技术支持

### 获取帮助

1. **查看文档**：
   - [MkDocs 官方文档](https://www.mkdocs.org/)
   - [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

2. **检查日志**：
   - GitHub Actions 日志
   - 本地构建日志

3. **社区支持**：
   - GitHub Issues
   - MkDocs 社区论坛

### 联系信息

- 📧 邮箱：your-email@example.com
- 🐛 问题反馈：[GitHub Issues](https://github.com/your-username/Financial-report/issues)
- 📖 项目文档：[项目说明](https://github.com/qipeijun/Financial-report)

## 🔄 更新日志

- **2025-01-15**：初始版本发布
- **2025-01-15**：添加自动化部署
- **2025-01-15**：优化导航生成

---

**祝您使用愉快！如有问题，请随时联系。** 🎉
