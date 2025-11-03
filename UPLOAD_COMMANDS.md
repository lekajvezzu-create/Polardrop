# 🚀 Exact Commands for Your GitHub Upload

## Your Repository Details
- **GitHub Username:** `lekajvezzu-create`
- **Repository:** `Polardrop`
- **Repository URL:** `https://github.com/lekajvezzu-create/Polardrop`
- **Visibility:** Public

---

## 📋 Step-by-Step Commands (Copy & Paste)

### Step 1: Open PowerShell
Press **Windows Key + X**, then select **"Windows PowerShell"**

### Step 2: Navigate to Project Folder
```powershell
cd "C:\Users\harsh\Desktop\Google_AP2"
```

### Step 3: Verify Git is Installed
```powershell
git --version
```
(Should show: `git version 2.x.x`)

### Step 4: Configure Git (First Time Only)
```powershell
git config --global user.name "lekajvezzu-create"
git config --global user.email "your-email@example.com"
```
**Replace `your-email@example.com` with your actual GitHub email**

### Step 5: Initialize Git Repository
```powershell
git init
```

### Step 6: Stage All Files
```powershell
git add .
```

### Step 7: Verify What Will Be Committed
```powershell
git status
```
(You should see all your folders and files listed)

### Step 8: Create Initial Commit
```powershell
git commit -m "Initial commit: Google AP2 E-commerce System with AP2 Protocol and Stripe Integration"
```

### Step 9: Add Remote Repository
```powershell
git remote add origin https://github.com/lekajvezzu-create/Polardrop.git
```

### Step 10: Verify Remote Connection
```powershell
git remote -v
```
(Should show your repository URL twice)

### Step 11: Fetch Existing Repository Content
Since the repository already exists with a README, we need to merge:

```powershell
git pull origin main --allow-unrelated-histories
```

If it asks for merge commit message, just press **Enter** to accept default.

### Step 12: Rename Branch to Main
```powershell
git branch -M main
```

### Step 13: Push to GitHub
```powershell
git push -u origin main
```

**When prompted:**
- **Username:** `lekajvezzu-create`
- **Password:** Your GitHub **Personal Access Token** (NOT your account password)

---

## 🔐 Creating Personal Access Token

If you don't have a Personal Access Token:

1. Go to: https://github.com/settings/tokens
2. Click **"Generate new token"** → **"Generate new token (classic)"**
3. **Note:** `Polardrop Upload`
4. **Expiration:** Choose your preference (30 days, 90 days, or no expiration)
5. **Select scopes:** Check **`repo`** (this gives full repository access)
6. Click **"Generate token"** at the bottom
7. **COPY THE TOKEN IMMEDIATELY** (you won't see it again!)
8. Paste it as your password when pushing

---

## ✅ Verify Upload

After pushing, visit:
**https://github.com/lekajvezzu-create/Polardrop**

You should see:
- ✅ Your `README.md` (merged with existing one)
- ✅ `Merchant agent/` folder
- ✅ `shopping agent/` folder
- ✅ `.gitignore` file
- ✅ All your code files
- ❌ NO `.env` files (good - they're protected by .gitignore)
- ❌ NO `node_modules/` (good - too large to upload)

---

## 🔄 If You Want to Replace Existing README Instead

If you want to **replace** the existing README in the repository (not merge):

### After Step 10, do this instead:

```powershell
# Force pull and overwrite local changes with remote
git pull origin main --allow-unrelated-histories -X theirs

# Or if you want to keep your local README and overwrite remote:
git pull origin main --allow-unrelated-histories -X ours
```

Then continue with Steps 12-13.

---

## 🚨 Troubleshooting

### Error: "remote origin already exists"
```powershell
git remote remove origin
git remote add origin https://github.com/lekajvezzu-create/Polardrop.git
```

### Error: "authentication failed"
- Make sure you're using **Personal Access Token**, not password
- Token must have **`repo`** scope checked
- Generate new token if needed

### Error: "failed to push some refs"
```powershell
git pull origin main --rebase
git push -u origin main
```

### Error: "refusing to merge unrelated histories"
You already have this covered with `--allow-unrelated-histories` flag.

---

## 📝 Complete Command Sequence (Copy All at Once)

```powershell
# Navigate to project
cd "C:\Users\harsh\Desktop\Google_AP2"

# Initialize Git
git init

# Configure Git (replace email)
git config --global user.name "lekajvezzu-create"
git config --global user.email "your-email@example.com"

# Stage all files
git add .

# Commit
git commit -m "Initial commit: Google AP2 E-commerce System with AP2 Protocol and Stripe Integration"

# Add remote
git remote add origin https://github.com/lekajvezzu-create/Polardrop.git

# Pull existing content (if any)
git pull origin main --allow-unrelated-histories

# Rename branch
git branch -M main

# Push to GitHub
git push -u origin main
```

Then enter your username and Personal Access Token when prompted!

---

**Ready? Start from Step 2 and work through each step! 🚀**

