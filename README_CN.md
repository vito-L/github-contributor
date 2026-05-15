# GitHub Contributor

> **[English](README.md)**

让 GitHub 热力图每天都是绿色的。

## ✨ 功能

- 🔄 自动提交 - 每天定时自动提交
- 📅 补历史 - 指定年份或最近N天，支持颜色深度

## 🚀 快速开始

### 1. Fork 本仓库

点击右上角的 Fork 按钮，将本仓库 Fork 到你的账号下。

### 2. 开启 GitHub Actions

进入你 Fork 的仓库，点击 Actions 标签，启用 GitHub Actions。

### 3. 完成

GitHub Actions 会每天自动提交一次，你的热力图会变绿。

## 📖 使用方法

### 自动提交

默认每天北京时间 9:00 自动提交一次，提交时间会随机延迟（0-5 分钟），更真实。

### 手动触发

进入 Actions 标签，点击 "Daily Commit"，再点击 "Run workflow" 即可手动触发。

### 补历史

进入 Actions 标签，点击 "Fill History"，再点击 "Run workflow" 即可。

| 参数 | 说明 | 默认值 |
|------|------|--------|
| year | 目标年份（留空则补最近N天） | - |
| days | 补多少天（仅在未指定年份时生效） | 365 |
| level | 颜色深度（1-4） | 2 |

#### 示例

**补最近一年**：
- year: 留空
- days: 365
- level: 2

**补指定年份**：
- year: 2023
- days: 留空
- level: 3

**颜色深度说明**：
- level 1: 最浅（每天1次提交）
- level 2: 浅（每天3次提交）
- level 3: 深（每天5次提交）
- level 4: 最深（每天10次提交）

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
