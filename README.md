# Personal Notes Sync

## About

This repository contains a script for syncing personal notes to GitHub using git.

## Setup Instructions

### Prerequisites

- Git installed on your system
- A GitHub account
- A Personal Access Token with repo permissions

### Creating Your Notes Repository

1. **Create a new repository on GitHub**
   - Go to github.com and create a new private repository
   - Name it something like `my-notes` or `personal-notes`

2. **Generate a Personal Access Token**
   - Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Click "Generate new token (classic)"
   - Give it a name like "Notes Sync"
   - Select scope: `repo` (full control of private repositories)
   - Set expiration (recommended: 90 days)
   - Click "Generate token" and copy it immediately

3. **Run the sync command**

Replace the placeholders with your actual information:

```bash
export T1="first_half_of_your_token" && \
export T2="second_half_of_your_token" && \
cd /tmp && \
git init notes && \
cd notes && \
git config user.email "your.email@example.com" && \
git config user.name "Your Name" > notes.txt && \
git add . && \
git commit -m "init" && \
git branch -m master main && \
git remote add origin https://${T1}${T2}@github.com/YOUR_USERNAME/YOUR_REPO.git && \
git push -u origin main
```

**Replace:**
- `first_half_of_your_token` and `second_half_of_your_token` with your GitHub token (split it in half)
- `your.email@example.com` with your email
- `Your Name` with your name
- `YOUR_USERNAME` with your GitHub username
- `YOUR_REPO` with your repository name

## After Initial Setup

To continue adding notes:

```bash
cd /tmp/notes
echo "My new note content" >> notes.txt
git add .
git commit -m "Added new note"
git push
```

## Security Notes

- Keep your Personal Access Token private
- Never commit tokens to git repositories
- Use environment variables or a password manager
- Rotate tokens regularly (every 90 days recommended)
- Use private repositories for personal notes

## Expected Output

After running the command successfully, you should see:

```
To https://github.com/YOUR_USERNAME/YOUR_REPO.git
 * [new branch]      main -> main
```

---

**Tip:** For better security, consider using SSH keys instead of HTTPS with tokens for long-term use.
