# GitHub Contributor

让 GitHub 热力图每天都是绿色的。

## ✨ 功能

- 🔄 自动提交 - 每天定时自动提交
- 📅 补历史 - 补过去一年的绿格子
- 🎲 随机时间 - 随机提交时间，更真实
- 📝 自定义内容 - 提交内容可配置
- 🔤 文字转热力图 - 在热力图上显示文字

## 🚀 快速开始

### 1. Fork 本仓库

点击右上角的 Fork 按钮，将本仓库 Fork 到你的账号下。

### 2. 开启 GitHub Actions

进入你 Fork 的仓库，点击 Actions 标签，启用 GitHub Actions。

### 3. 完成

GitHub Actions 会每天自动提交一次，你的热力图会变绿。

## 📖 使用方法

### 自动提交

默认每天北京时间 9:00 自动提交一次，提交时间会随机延迟（0-1 小时），更真实。

### 手动触发

进入 Actions 标签，点击 "Daily Commit"，再点击 "Run workflow" 即可手动触发。

### 补历史

进入 Actions 标签，点击 "Fill History"，再点击 "Run workflow" 即可补历史。

| 参数 | 说明 | 默认值 |
|------|------|--------|
| days | 补多少天 | 365 |

补历史功能会：
- 生成过去 N 天的提交
- 每个提交使用随机时间（更真实）
- 自动跳过已有提交的日期

### 文字转热力图

进入 Actions 标签，点击 "Text to Heatmap"，再点击 "Run workflow" 即可。

| 参数 | 说明 | 默认值 |
|------|------|--------|
| text | 要显示的文字（A-Z, 0-9, 空格） | HELLO |
| year | 目标年份 | 2024 |
| level | 贡献级别（1-4） | 4 |

功能特点：
- 支持 A-Z、0-9、空格
- 支持选择年份（从注册年份到当前年份）
- 支持调整颜色深度
- 文字居中显示

### 自定义提交时间

修改 `.github/workflows/commit.yml` 中的 cron 表达式：

```yaml
schedule:
  - cron: '0 1 * * *'  # UTC 1:00 = 北京时间 9:00
```

### 自定义提交内容

修改 `config.json` 文件：

```json
{
  "commit_message": "feat: contribution {date}",
  "content_templates": [
    "Contribution on {date} {time}",
    "Daily commit: {date}",
    "Another day, another commit: {date}"
  ],
  "random_content": true
}
```

| 变量 | 说明 |
|------|------|
| {date} | 日期（YYYY-MM-DD） |
| {time} | 时间（HH:MM:SS） |

## ⚙️ 配置

| 配置项 | 说明 | 默认值 |
|--------|------|--------|
| cron | 提交时间 | 每天 UTC 1:00 |
| commit_message | 提交信息 | feat: contribution YYYY-MM-DD |

## 📝 License

[MIT](LICENSE)
