# 📤 Step-by-Step GitHub Upload Guide

Follow these exact steps to upload your Google AP2 project to GitHub.

---

## 📋 Prerequisites Checklist

Before starting, make sure you have:
- [ ] Git installed on your computer
- [ ] GitHub account created
- [ ] GitHub username ready
- [ ] Repository name decided (e.g., `google-ap2` or `ap2-ecommerce`)
- [ ] Decided on Public or Private repository

---

## 🔧 Step 1: Verify Git is Installed

Open **PowerShell** (Windows key + X, then select "Windows PowerShell"):

```powershell
git --version
```

**If Git is NOT installed:**
1. Download from: https://git-scm.com/download/win
2. Install with default settings
3. Restart PowerShell

**Expected output:** `git version 2.x.x` or higher

---

## 🗂️ Step 2: Navigate to Project Folder

In PowerShell, type:

```powershell
cd "C:\Users\harsh\Desktop\Google_AP2"
```

Verify you're in the right folder:
```powershell
dir
```

You should see `Merchant agent`, `shopping agent`, `README.md`, etc.

---

## 📝 Step 3: Configure Git (First Time Only)

If this is your first time using Git on this computer:

```powershell
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Replace with your actual name and GitHub email address.**

---

## 🎬 Step 4: Initialize Git Repository

```powershell
git init
```

**Expected output:** `Initialized empty Git repository in C:/Users/harsh/Desktop/Google_AP2/.git`

---

## ✅ Step 5: Verify .gitignore Exists

Check that `.gitignore` file exists:

```powershell
dir .gitignore
```

If it doesn't exist or you see an error, the file should already be there (we created it). If missing, create it with the content from our `.gitignore` file.

---

## 📦 Step 6: Stage All Files

Add all files to Git:

```powershell
git add .
```

**Verify what will be committed:**

```powershell
git status
```

You should see:
- ✅ All your folders (`Merchant agent/`, `shopping agent/`)
- ✅ All your files (README.md, package.json files, etc.)
- ❌ NO `.env` files (these are ignored - good!)
- ❌ NO `node_modules/` folders (these are ignored - good!)

---

## 💾 Step 7: Create Initial Commit

```powershell
git commit -m "Initial commit: Google AP2 E-commerce System with AP2 Protocol and Stripe Integration"
```

**Expected output:** A list of files being committed.

---

## 🌐 Step 8: Create GitHub Repository

**Option A: Create via GitHub Website (Recommended)**

1. Open browser and go to: **https://github.com/new**
2. **Repository name:** Enter your chosen name (e.g., `google-ap2`)
3. **Description (optional):** `E-commerce platform with AP2 Payment Protocol and AI-powered shopping search`
4. **Visibility:** 
   - Select **Public** (anyone can see)
   - OR **Private** (only you can see)
5. **IMPORTANT:** 
   - ❌ **DO NOT** check "Add a README file"
   - ❌ **DO NOT** check "Add .gitignore"
   - ❌ **DO NOT** check "Choose a license"
6. Click **"Create repository"** (green button)

**Option B: Create via GitHub CLI (if installed)**

```powershell
gh repo create google-ap2 --public --description "E-commerce platform with AP2 Payment Protocol"
```

---

## 🔗 Step 9: Connect Local Repository to GitHub

**Get your repository URL:**
- If you created it via website, copy the URL from GitHub (it will show after creation)
- Format: `https://github.com/YOUR_USERNAME/REPO_NAME.git`

**Add remote repository:**

```powershell
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

**Example:**
```powershell
git remote add origin https://github.com/johnsmith/google-ap2.git
```

**Verify connection:**

```powershell
git remote -v
```

Should show:
```
origin  https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git (fetch)
origin  https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git (push)
```

---

## 🚀 Step 10: Push to GitHub

**Rename branch to main (if needed):**

```powershell
git branch -M main
```

**Push your code:**

```powershell
git push -u origin main
```

**If prompted for authentication:**

1. **Username:** Your GitHub username
2. **Password:** Your GitHub **Personal Access Token** (NOT your account password)
   
   **To create a Personal Access Token:**
   - Go to: https://github.com/settings/tokens
   - Click "Generate new token" → "Generate new token (classic)"
   - Give it a name: "Google AP2 Upload"
   - Select scope: **repo** (check the box)
   - Click "Generate token"
   - **COPY THE TOKEN IMMEDIATELY** (you won't see it again!)
   - Paste it as your password

**Expected output:**
```
Enumerating objects: XXX, done.
Counting objects: 100% (XXX/XXX), done.
Delta compression using up to X threads
Compressing objects: 100% (XXX/XXX), done.
Writing objects: 100% (XXX/XXX), done.
To https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

---

## ✅ Step 11: Verify Upload

1. Go to your GitHub repository in browser:
   ```
   https://github.com/YOUR_USERNAME/YOUR_REPO_NAME
   ```

2. **Check the following:**
   - ✅ README.md is visible
   - ✅ `Merchant agent/` folder exists
   - ✅ `shopping agent/` folder exists
   - ✅ All `package.json` files are there
   - ✅ `.gitignore` file is there
   - ❌ NO `.env` files visible (good - they're private!)
   - ❌ NO `node_modules/` visible (good - too large!)

---

## 🎯 Complete! Your Code is on GitHub

Your repository URL:
```
https://github.com/YOUR_USERNAME/YOUR_REPO_NAME
```

---

## 🔄 Future Updates

When you make changes to your code:

```powershell
cd "C:\Users\harsh\Desktop\Google_AP2"
git add .
git commit -m "Description of your changes"
git push
```

---

## ❓ Troubleshooting

### Error: "fatal: remote origin already exists"
**Solution:**
```powershell
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

### Error: "Authentication failed"
**Solution:**
- Use Personal Access Token, not password
- Generate new token at: https://github.com/settings/tokens

### Error: "refusing to merge unrelated histories"
**Solution:**
```powershell
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### Error: "repository not found"
**Solution:**
- Check repository URL is correct
- Verify repository exists on GitHub
- Check you have access to the repository

### Files not showing on GitHub
**Solution:**
```powershell
git status  # Check if files are staged
git add .    # Stage all files again
git commit -m "Add missing files"
git push
```

---

## 📞 Need Help?

- **Git Documentation:** https://git-scm.com/doc
- **GitHub Help:** https://docs.github.com
- **Creating Personal Access Token:** https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

---

**Ready to upload? Start from Step 1 and follow each step! 🚀**

