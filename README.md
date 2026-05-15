# GitHub Contributor

Keep your GitHub contribution graph green every day.

> **[中文文档](README_CN.md)**

## ✨ Features

- 🔄 **Auto Commit** - Automatic daily commits
- 📅 **Backfill History** - Fill specific years or recent N days with color depth control

## 🚀 Quick Start

### 1. Fork this repository

Click the Fork button in the top right corner to fork this repository to your account.

### 2. Enable GitHub Actions

Go to your forked repository, click the Actions tab, and enable GitHub Actions.

### 3. Done

GitHub Actions will automatically commit once a day, and your contribution graph will turn green.

## 📖 Usage

### Auto Commit

By default, commits are made daily at 9:00 AM Beijing Time (UTC 1:00) with a random delay (0-5 minutes) for a more natural look.

### Manual Trigger

Go to the Actions tab, click "Daily Commit", then click "Run workflow" to trigger manually.

### Backfill History

Go to the Actions tab, click "Fill History", then click "Run workflow".

| Parameter | Description | Default |
|-----------|-------------|---------|
| year | Target year (leave empty to backfill recent N days) | - |
| days | Number of days to backfill (only when year is not specified) | 365 |
| level | Color depth (1-4) | 2 |

#### Examples

**Backfill last year**:
- year: (leave empty)
- days: 365
- level: 2

**Backfill specific year**:
- year: 2023
- days: (leave empty)
- level: 3

**Color depth levels**:
- level 1: Lightest (1 commit per day)
- level 2: Light (3 commits per day)
- level 3: Dark (5 commits per day)
- level 4: Darkest (10 commits per day)

### Customize Commit Time

Edit the cron expression in `.github/workflows/commit.yml`:

```yaml
schedule:
  - cron: '0 1 * * *'  # UTC 1:00 = Beijing Time 9:00
```

### Customize Commit Content

Edit the `config.json` file:

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

| Variable | Description |
|----------|-------------|
| {date} | Date (YYYY-MM-DD) |
| {time} | Time (HH:MM:SS) |

## ⚙️ Configuration

| Config | Description | Default |
|--------|-------------|---------|
| cron | Commit schedule | Daily at UTC 1:00 |
| commit_message | Commit message | feat: contribution YYYY-MM-DD |

## 📝 License

[MIT](LICENSE)
