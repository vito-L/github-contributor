# GitHub Contributor

让 GitHub 热力图每天都是绿色的。

## ✨ 功能

- 🔄 自动提交 - 每天定时自动提交
- 📅 补历史 - 补过去一年的绿格子
- 🎲 随机时间 - 随机提交时间，更真实
- 📝 自定义内容 - 提交内容可配置

## 🚀 快速开始

### 1. Fork 本仓库

点击右上角的 Fork 按钮，将本仓库 Fork 到你的账号下。

### 2. 开启 GitHub Actions

进入你 Fork 的仓库，点击 Actions 标签，启用 GitHub Actions。

### 3. 完成

GitHub Actions 会每天自动提交一次，你的热力图会变绿。

## 📖 使用方法

### 自动提交

默认每天北京时间 9:00 自动提交一次。

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

### 自定义提交时间

修改 `.github/workflows/commit.yml` 中的 cron 表达式：

```yaml
schedule:
  - cron: '0 1 * * *'  # UTC 1:00 = 北京时间 9:00
```

### 自定义提交内容

修改 `.github/workflows/commit.yml` 中的提交内容：

```yaml
- name: Make commit
  run: |
    # 修改这一行来改变提交内容
    echo "Your custom content" >> contributions/$(date '+%Y-%m-%d').txt
```

## ⚙️ 配置

| 配置项 | 说明 | 默认值 |
|--------|------|--------|
| cron | 提交时间 | 每天 UTC 1:00 |
| commit_message | 提交信息 | feat: contribution YYYY-MM-DD |

## 📝 License

[MIT](LICENSE)
