# 🚀 Quick GitHub Upload Guide (5 Minutes)

## Step-by-Step Instructions

### ⚡ Fastest Method: VS Code

1. **Open VS Code** in `C:\Users\harsh\Desktop\Google_AP2`

2. **Source Control Panel** (Ctrl+Shift+G)
   - Click "Initialize Repository" (if needed)
   - Stage all files (click + next to "Changes")
   - Enter commit message: `"Initial commit: Google AP2 E-commerce System"`
   - Click "Commit"

3. **Publish to GitHub**
   - Click "Publish Branch" button
   - Choose GitHub account
   - Enter repository name: `google-ap2` (or your preferred name)
   - Choose visibility: **Public** or **Private**
   - Click **Publish**

✅ **Done!** Your code is now on GitHub.

---

### 🔧 Alternative: Git Command Line

Open **PowerShell** or **Git Bash** in your project folder:

```powershell
# Navigate to project
cd "C:\Users\harsh\Desktop\Google_AP2"

# Initialize Git (if not done)
git init

# Stage all files
git add .

# Commit
git commit -m "Initial commit: Google AP2 E-commerce System"

# Add GitHub remote (replace with your repo URL)
git remote add origin https://github.com/YOUR_USERNAME/google-ap2.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Need to create the repository first?**
1. Go to https://github.com/new
2. Name it: `google-ap2`
3. Choose Public/Private
4. **DON'T** initialize with README (we already have one)
5. Click "Create repository"
6. Copy the repository URL and use it in the `git remote add` command above

---

### 📦 What Gets Uploaded

✅ **Included:**
- All source code
- `package.json` files
- README files
- Configuration files
- Public assets

❌ **Excluded** (by `.gitignore`):
- `node_modules/` (too large, users will run `npm install`)
- `.env` files (contain API keys - sensitive!)
- Log files
- Secret keys in `secrets/` folder
- Build outputs

---

### ⚠️ Important: Environment Files

After cloning, users need to:
1. Copy `env.example` to `.env` in each component
2. Add their own API keys
3. Run `npm install` in each folder

---

### 🔍 Verify Upload

After uploading, visit:
```
https://github.com/YOUR_USERNAME/google-ap2
```

You should see:
- ✅ README.md
- ✅ All project folders
- ✅ package.json files
- ❌ No .env files (good - they're private)
- ❌ No node_modules (good - too large)

---

## 🎯 Quick Checklist

- [ ] Created `.gitignore` file (✅ Already done)
- [ ] Created root `README.md` (✅ Already done)
- [ ] Committed all files
- [ ] Pushed to GitHub
- [ ] Verified upload on GitHub.com
- [ ] Confirmed sensitive files (.env, secrets) are NOT visible

---

**Need help?** Check the main README.md for detailed project information.

