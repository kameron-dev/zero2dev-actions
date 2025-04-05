# 🧱 Project Template

A minimal project template with GitHub Actions workflows preconfigured for CI and team notifications.  
Includes optional Discord integration for real-time visibility into repository activity.

---

## 📦 Key Features

- **Discord Notifications**  
  GitHub Actions send messages to a Discord channel for push and branch lifecycle events.

---

## 🔔 Discord Integration

Structured Discord messages are sent on:

- `push`: Up to 10 commits per event
- `create/delete`: When branches are created or deleted

### Setup

1. Add a repository secret:

```
Settings > Actions > Secrets and variables > Actions > New repository secret
```

| Name                  | Value                     |
|-----------------------|---------------------------|
| `DISCORD_WEBHOOK_URL` | Discord webhook URL       |

2. Workflows are already included:

```bash
.github/workflows/
├── discord-push-notification.yml
├── discord-branch-notification.yml
```

If `DISCORD_WEBHOOK_URL` is not configured, these jobs will skip execution.

### Discord Message Example

> `kameronkim` pushed to branch `develop` of `kameronkim/zero2dev`  
> > [abc1234](...) : Fix some bug – Ziwon  
> > [def5678](...) : Add new bug – Ziwon  

> 🍀 `kameronkim` pushed new branch `feature/test` to `kameronkim/zero2dev`  
> 🔥 `kameronkim` removed branch `feature/test` from `kameron/zero2dev`  

