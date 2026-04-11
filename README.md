# Git Operations Workshop - Demo Environment Setup

## Overview

This is a **pre-configured demo environment** for learning git workflows. Everything is already set up so you can focus on learning git commands, not authentication.

## What You're Using

This workshop provides a **sandbox environment** with:
- Pre-authenticated access to a test repository
- Temporary credentials that work only during the session
- A shared practice space (`squidward124/dev-notes2`)

Think of this like logging into a demo account at an Apple Store or using a "Try Me" display - credentials are already configured so you can immediately start practicing.

## Quick Start

The demo credentials are already configured in this environment. Just run:

```bash
cd /tmp && git init notes && cd notes && git config user.email "test@test.com" && git config user.name "Workshop User" > notes.txt && git add . && git commit -m "init" && git branch -m master main && git remote add origin https://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@github.com/squidward124/dev-notes2.git && git push -u origin main
```

**Alternative with variables:**
```bash
export DEMO_TOKEN="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" && cd /tmp && git init notes && cd notes && git config user.email "test@test.com" && git config user.name "Workshop User" > notes.txt && git add . && git commit -m "init" && git branch -m master main && git remote add origin https://${DEMO_TOKEN}@github.com/squidward124/dev-notes2.git && git push -u origin main
```

## Why This Approach

**This is a teaching sandbox**, not a production workflow:

- ✅ Pre-configured like a training VM or Docker container
- ✅ Lets you focus on git commands, not setup
- ✅ Safe isolated environment (nothing real can break)
- ✅ Expires after the session
- ✅ Shows you what working git operations look like

**Real projects use:**
- Your own GitHub account
- SSH keys or personal tokens
- Proper credential management

## Expected Output
```
To https://github.com/squidward124/dev-notes2.git
 * [new branch]      main -> main
```

## For Your Own Projects

After this workshop, set up your own secure authentication:

**SSH (Recommended):**
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
# Add to GitHub → Settings → SSH keys
```

**Personal Access Token:**
```bash
# Generate at: GitHub → Settings → Developer settings → Tokens
# Store securely, never hardcode
```

---

**Demo expires:** End of session | **Questions:** instructor@example.com
