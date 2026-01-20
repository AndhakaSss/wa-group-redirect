# Bot Repository - Quick Fix for Vercel

## Problem: "Error creating build plan"

This happens when Vercel can't detect your project type.

## Solution: Add these 3 files to your bot repo:

### 1. requirements.txt (MUST HAVE)
```
redis==5.0.6
python-telegram-bot==21.0.1
python-dotenv==1.0.1
```

### 2. Procfile (MUST HAVE)
```
worker: python bot.py
```

### 3. .gitignore (optional but good)
```
__pycache__/
*.py[cod]
.env
.env.local
*.log
```

## Steps to Fix:

1. **In your bot GitHub repo, create these files:**
   - Click "Add file" → "Create new file"
   - Name: `requirements.txt` → Paste the content above
   - Name: `Procfile` → Paste `worker: python bot.py`
   - Commit the files

2. **In Vercel:**
   - Go to your bot service
   - Settings → Deploy
   - Set Start Command: `python bot.py`
   - Variables tab → Add all environment variables
   - Click "Redeploy"

3. **Check logs:**
   - Should see "Bot is running..." message
   - If you see errors, check the Variables are set correctly

## If still failing:

1. Delete the Vercel service
2. Create new service from GitHub repo (with all files)
3. Vercel should auto-detect Python from requirements.txt

