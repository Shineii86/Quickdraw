<div align="center">

[![Quickdraw Banner](https://raw.githubusercontent.com/Shineii86/Quickdraw/main/images/Quickdraw.png)](https://github.com/Shineii86/Quickdraw)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Shineii86/Quickdraw/blob/main/notebooks/Quickdraw.ipynb)
[![Python 3.8+](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[![GitHub Stars](https://img.shields.io/github/stars/Shineii86/Quickdraw?style=for-the-badge)](https://github.com/Shineii86/Quickdraw/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/Shineii86/Quickdraw?style=for-the-badge)](https://github.com/Shineii86/Quickdraw/fork)

A **fully automated** Python script that runs in **Google Colab** to earn the **Quickdraw** achievement by opening and immediately closing an issue or pull request.

</div>

---

> [!WARNING]
> **This script automates interactions with GitHub to artificially trigger the Quickdraw achievement.**
> - **Use responsibly.** Inflating achievements may be viewed negatively by potential employers or collaborators, and may violate GitHub's Terms of Service.
> - You need a **Personal Access Token (classic)** with `repo` scope for your account.
> - The script creates a repository, opens an issue or PR, and closes it within seconds.
> - This tool is intended for **educational purposes and personal experimentation** only.

---

## 📖 Table of Contents

- [What is This Tool?](#-what-is-this-tool)
- [Why Use This Method?](#-why-use-this-method)
- [Prerequisites](#-prerequisites)
  - [1. Required Accounts](#1-required-accounts)
  - [2. Generate a Personal Access Token (Classic)](#2-generate-a-personal-access-token-classic)
- [Step-by-Step Guide](#-step-by-step-guide)
- [Configuration Options](#-configuration-options)
- [How It Works](#-how-it-works-technical-overview)
- [Troubleshooting](#-troubleshooting)
- [License & Disclaimer](#-license--disclaimer)

---

## 🎯 What is This Tool?

This tool automates the process of earning the **Quickdraw** achievement on GitHub. Quickdraw is awarded when a user closes an issue or pull request within 5 minutes of opening it.

Using the **GitHub REST API**, the script:
1. Creates a public repository (or uses an existing one).
2. Opens either an **issue** or a **pull request** (your choice).
3. Waits a few seconds.
4. Closes the issue or PR immediately.

> [!NOTE]
>  The achievement may take a few minutes to several hours to appear on your profile.

---

## ✅ Why Use This Method?

| Feature                      | Benefit                                                                 |
|------------------------------|-------------------------------------------------------------------------|
| ☁️ **No PC Required**         | Runs entirely in Google Colab (cloud‑based). Works on any device with a browser. |
| 🔁 **Fully Automated**        | Creates the repo, opens the item, and closes it — all automatically.     |
| 🎯 **Issue or PR**            | Choose whether to use an issue or a pull request — both work!            |
| 🛡️ **REST API**               | Uses official GitHub REST APIs — no browser automation or scraping.      |
| 📦 **Minimal Dependencies**   | Only requires `requests` and standard libraries.                         |

---

## 🧰 Prerequisites

### 1. Required Accounts

- **One GitHub account** – This account will receive the Quickdraw achievement.

### 2. Generate a Personal Access Token (Classic)

You need a **Personal Access Token (Classic)** for your account with the `repo` scope.

> [!IMPORTANT]
> **Required scope:**
> - `repo` – Grants full control of private repositories (required for creating repos, issues, and PRs).

#### How to Create a Token

1. Log in to your account and go to **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**.
2. Click **Generate new token** → **Generate new token (classic)**.
3. Give it a descriptive **Note** (e.g., `Quickdraw Script`).
4. Set an **Expiration** (e.g., 7 days – recommended for security).
5. Under **Select scopes**, check the following box:
   - ☑️ **repo** (this automatically selects all sub‑scopes under `repo`)
6. Click **Generate token**.
7. **Copy the token immediately** (it starts with `ghp_`) and store it securely. You will not be able to see it again.

> 🔒 **Security Note:** Treat this token like a password. Never commit it to a public repository or share it with anyone.

---

## 📥 How to Deploy

### 1️⃣ One‑Click Colab

<a href="https://colab.research.google.com/github/Shineii86/Quickdraw/blob/main/notebooks/Quickdraw.ipynb">
  <img src="https://user-images.githubusercontent.com/125879861/255389999-a0d261cf-893a-46a7-9a3d-2bb52811b997.png" alt="Open In Colab" width="200px">
</a>

### 2️⃣ Fill in the Configuration Form

Inside the Colab notebook, you'll find a single configuration cell with form fields:

| Variable       | Description                                                               | Example Value               |
|----------------|---------------------------------------------------------------------------|-----------------------------|
| `USERNAME`     | Your GitHub handle (to earn the achievement)                              | `"Shineii86"`               |
| `TOKEN`        | Personal Access Token with `repo` scope                                   | `"ghp_abc123..."`           |
| `REPO_NAME`    | Repository name (will be created if it doesn't exist)                     | `"quickdraw-demo"`          |
| `ITEM_TYPE`    | Type of item to create and close: `"issue"` or `"pull_request"`           | `"issue"`                   |
| `CLOSE_DELAY`  | Seconds to wait before closing (must be < 300)                            | `2`                         |

### 3️⃣ Run the Notebook

Click **Runtime → Run all** (or press `Ctrl+F9`). The notebook will:
- Install `requests`
- Create a public repository
- Open an issue (or PR)
- Wait a few seconds
- Close the issue (or PR)

You'll see real‑time output like:

```
🤠 Quickdraw Achievement Helper for user 'Shineii86'
Repository: Shineii86/quickdraw-demo
Item type: issue
Close delay: 2 seconds

📦 Creating repository 'quickdraw-demo'...
   ✅ Repository created: https://github.com/Shineii86/quickdraw-demo
📝 Creating issue...
   ✅ Issue created: https://github.com/Shineii86/quickdraw-demo/issues/1
⏳ Waiting 2 seconds before closing...
🔒 Closing issue #1...
   ✅ Issue closed

==================================================
✨ Success! Issue opened and closed within 2 seconds.
📊 Check your profile: https://github.com/Shineii86
```

### 4️⃣ Check Your Achievements

1. Go to your GitHub profile: `https://github.com/YOUR_USERNAME`
2. Scroll down to the **Achievements** section (if you already have some) or visit `https://github.com/settings/achievements`.
3. **Quickdraw** should appear within a few minutes to a few hours.

---

## ⚙️ Configuration Options

| Parameter     | Default     | Description                                                                                                   |
|---------------|-------------|---------------------------------------------------------------------------------------------------------------|
| `USERNAME`    | —           | The GitHub username that will earn the achievement.                                                            |
| `TOKEN`       | —           | PAT for your account with `repo` scope.                                                                        |
| `REPO_NAME`   | —           | Repository name. Will be created if it doesn't exist.                                                          |
| `ITEM_TYPE`   | `"issue"`   | Choose `"issue"` or `"pull_request"`. Both work for Quickdraw.                                                 |
| `CLOSE_DELAY` | `2`         | Seconds to wait before closing. Must be less than 300 (5 minutes).                                             |

---

## 🔬 How It Works (Technical Overview)

The script interacts with the **GitHub REST API v3** using the following endpoints:

1. **`POST /user/repos`** – Creates a new public repository.
2. **`POST /repos/{owner}/{repo}/issues`** – Creates a new issue.
3. **`PATCH /repos/{owner}/{repo}/issues/{number}`** – Closes the issue (by setting `state: "closed"`).

**For Pull Request mode, additional endpoints are used:**
- **`POST /repos/{owner}/{repo}/git/refs`** – Creates a new branch.
- **`PUT /repos/{owner}/{repo}/contents/{path}`** – Creates/updates a file.
- **`POST /repos/{owner}/{repo}/pulls`** – Creates a pull request.
- **`PATCH /repos/{owner}/{repo}/pulls/{number}`** – Closes the pull request.

**Workflow (Issue Mode):**

```
┌─────────────────┐     ┌─────────────────────┐     ┌──────────────────────┐
│    Your Account    │───▶│    Create Repository    │──▶│    Repository Created    │
└─────────────────┘     └─────────────────────┘     └──────────────────────┘
                                                               │
                                                               ▼
┌─────────────────┐     ┌─────────────────┐     ┌──────────────────────┐
│    Your Account    │───▶│    Create Issue    │───▶│      Issue Opened        │
└─────────────────┘     └─────────────────┘     └──────────────────────┘
                                      │
                                      ▼ (after 2 seconds)
                            ┌──────────────────────┐
                            │      Close Issue         │
                            │    (within 5 minutes)    │
                            └──────────────────────┘
                                      │
                                      ▼
                            🏆 Quickdraw Earned!
```

---

## 🆘 Troubleshooting

| Issue                                                      | Solution                                                                                     |
|------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| `API request failed: 404`                                  | The repository name may be taken or you don't have access. Try a different `REPO_NAME`.       |
| `API request failed: 422` (already exists)                 | The repository already exists. The script will use the existing one.                          |
| `Bad credentials`                                           | Your `TOKEN` is incorrect, expired, or lacks the `repo` scope.                                |
| Achievement not appearing after several hours               | Wait up to 24 hours. Ensure the repository is **public** and the item was closed within 5 minutes. |
| Issue/PR closed but not within 5 minutes                    | Reduce `CLOSE_DELAY`. The default 2 seconds is safe.                                           |

---

## 📄 License & Disclaimer

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

> [!WARNING]
> This script is intended for **educational purposes and personal experimentation** only. Artificially triggering achievements may be viewed negatively by potential employers or collaborators, and may violate GitHub's Terms of Service. The author is not responsible for any consequences arising from misuse of this tool, including but not limited to account suspension, damage to professional reputation, or violation of platform terms.

---

### 🔗 Quick Links

- [Google Colab](https://colab.research.google.com/)
- [GitHub Personal Access Tokens](https://github.com/settings/tokens)
- [GitHub REST API Documentation](https://docs.github.com/en/rest)
- [GitHub Achievements](https://github.com/settings/achievements)

---

## 💕 Loved My Work?

🚨 [Follow me on GitHub](https://github.com/Shineii86)

⭐ [Give a star to this project](https://github.com/Shineii86/Quickdraw)

<div align="center">

<a href="https://github.com/Shineii86/Quickdraw">
<img src="https://github.com/Shineii86/AniPay/blob/main/Source/Banner6.png" alt="Banner">
</a>
  
  *For inquiries or collaborations*
     
[![Telegram Badge](https://img.shields.io/badge/-Telegram-2CA5E0?style=flat&logo=Telegram&logoColor=white)](https://telegram.me/Shineii86 "Contact on Telegram")
[![Instagram Badge](https://img.shields.io/badge/-Instagram-C13584?style=flat&logo=Instagram&logoColor=white)](https://instagram.com/ikx7.a "Follow on Instagram")
[![Pinterest Badge](https://img.shields.io/badge/-Pinterest-E60023?style=flat&logo=Pinterest&logoColor=white)](https://pinterest.com/ikx7a "Follow on Pinterest")
[![Gmail Badge](https://img.shields.io/badge/-Gmail-D14836?style=flat&logo=Gmail&logoColor=white)](mailto:ikx7a@hotmail.com "Send an Email")

  <sup><b>Copyright © 2026 <a href="https://telegram.me/Shineii86">Shinei Nouzen</a> All Rights Reserved</b></sup>

![Last Commit](https://img.shields.io/github/last-commit/Shineii86/Quickdraw?style=for-the-badge)

</div>
