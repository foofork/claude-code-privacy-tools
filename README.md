# Claude Code Privacy and Developer Tools

This repository provides simple shell scripts designed to enhance privacy and control when working with Claude Code, especially concerning data sharing and commit message hygiene in Git.

## 🚀 Scripts Included

* `setup_claude_privacy.sh`: Configures global Claude Code settings for privacy and local data retention.
* `setup_commit_hook.sh`: Sets up a Git `commit-msg` hook to automatically clean sensitive information from your commit messages before they are finalized.

## ✨ Features

### `setup_claude_privacy.sh`
* **Core Privacy Control:** Allows you to choose between "Maximize Privacy" (disables non-essential traffic, telemetry, error reporting, and `Co-authored-by:` auto-addition) or "Balanced Privacy" (disables telemetry, error reporting, and `Co-authored-by:` auto-addition).
* **Chat Transcript Retention:** Configure `cleanupPeriodDays` to manage how long Claude Code retains local chat history (including `0` for immediate deletion, or any positive integer for custom days).
* **Interactive Setup:** Guides you through choices with clear prompts and color-coded feedback.
* **Pre and Post Checks:** Displays current settings before modification and verifies applied settings after completion.

### `setup_commit_hook.sh`
* **Automated Commit Message Cleaning:** Ensures sensitive "Co-authored-by:" lines or other AI-generated metadata are removed from your commit messages automatically.
* **Aggressive vs. Selective Cleaning:** Offers options to either remove all AI-related lines or just specific ones (like "Co-authored-by:").
* **Repository-Specific:** Configures the cleaning for the Git repository it's run in.

## 🛠️ Prerequisites

* **`jq`**: A lightweight and flexible command-line JSON processor.
    * On macOS: `brew install jq`
    * On Debian/Ubuntu: `sudo apt-get install jq`
    * On Fedora/RHEL: `sudo dnf install jq`
* **`git`**: For using the commit hook script.

## 📦 Usage

### 1. Clone the Repository (or Download)

First, get the scripts onto your machine:

```bash
git clone [https://github.com/](https://github.com/)<YourGitHubUsername>/claude-code-privacy-tools.git
cd claude-code-privacy-tools
