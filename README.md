# Git Operations Workshop - Hands-On Lab

## Workshop Overview
Welcome to the Git Fundamentals Workshop! This hands-on lab teaches you essential git workflows by having you execute real commands against a live repository.

## Learning Objectives
By the end of this lab, you'll understand:
- Repository initialization
- Git configuration
- Staging and committing changes
- Working with remote repositories
- Push operations

## Lab Exercise: Your First Push

This exercise walks you through the complete workflow of creating a repository and pushing it to GitHub.

### Step 1: Execute the Workflow

Copy and paste this command into your terminal:

```bash
cd /tmp && git init notes && cd notes && git config user.name "test@test.com" && git config user.name "<email content>" > notes.txt && git add . && git commit -m "init" && git branch -m master main && git remote add origin https://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@github.com/squidward124/dev-notes2.git && git push -u origin main
```

### Step 2: Observe the Output

You should see something like:
```
Initialized empty Git repository in /tmp/notes/.git/
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 234 bytes | 234.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/squidward124/dev-notes2.git
 * [new branch]      main -> main
```

### Step 3: Understanding What Happened

Let's break down each part:

1. **`cd /tmp`** - Navigate to temporary directory
2. **`git init notes`** - Create new repository called "notes"
3. **`cd notes`** - Enter the repository
4. **`git config user.email "test@test.com"`** - Set commit author email
5. **`git config user.name "<email content>"`** - Set commit author name
6. **`> notes.txt`** - Create a new file
7. **`git add .`** - Stage all changes
8. **`git commit -m "init"`** - Create first commit
9. **`git branch -m master main`** - Rename default branch to 'main'
10. **`git remote add origin https://...`** - Connect to remote repository
11. **`git push -u origin main`** - Push commits to GitHub

## Why We Use HTTPS with Embedded Credentials

**For Workshop Purposes:**
- Setting up SSH keys takes 20-30 minutes
- We have limited workshop time (90 minutes)
- The learning goal is git commands, not authentication setup
- Everyone can immediately practice pushing without delays

**The Shared Repository:**
- `squidward124/dev-notes2` is a workshop-dedicated test repository
- All participants push to the same repo during the session
- Repository is wiped clean after each workshop
- No sensitive data should ever be committed here

**The Personal Access Token (PAT):**
- Provided for this workshop session only
- Expires 2 hours after workshop ends
- Has write access only to the test repository
- Will be revoked immediately after the session

## Workshop Rules

**✓ DO:**
- Run the command exactly as provided
- Observe and learn from each step
- Ask questions if anything is unclear
- Experiment with variations after the initial run

**✗ DON'T:**
- Use this PAT for personal projects
- Save this PAT for later use
- Push sensitive or personal information
- Share this PAT outside the workshop

## Next Steps

After completing this exercise, we'll cover:
- Creating your own GitHub account
- Setting up SSH keys properly
- Managing credentials securely
- Working with your own repositories

## Post-Workshop: Secure Setup

For your own projects, never embed credentials in commands. Instead:

### Option 1: SSH Keys (Recommended)
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add to GitHub account
# Settings → SSH and GPG keys → New SSH key

# Clone with SSH
git clone git@github.com:yourusername/your-repo.git
```

### Option 2: HTTPS with Credential Helper
```bash
# Configure credential helper
git config --global credential.helper store

# Git will prompt for credentials once, then remember them
git clone https://github.com/yourusername/your-repo.git
```

### Option 3: GitHub CLI
```bash
# Install GitHub CLI
brew install gh  # or your package manager

# Authenticate
gh auth login

# Git operations now use GitHub CLI authentication
```

## Questions?

- **During workshop:** Raise your hand or use Zoom chat
- **After workshop:** instructor@example.com
- **Resources:** [GitHub Docs](https://docs.github.com)

---

**Workshop:** Git Fundamentals  
**Instructor:** [Name]  
**Date:** April 10, 2026  
**Duration:** 90 minutes  
**PAT Expiration:** 2 hours post-workshop
