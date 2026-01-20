# Bot Repository Setup for Vercel

## Files needed in your bot repo:

1. **bot.py** ✅ (you already have this)

2. **requirements.txt** (create this file):
```
redis==5.0.6
python-telegram-bot==21.0.1
python-dotenv==1.0.1
```

3. **Procfile** (create this file):
```
worker: python bot.py
```

4. **runtime.txt** (optional, but recommended):
```
python-3.11.0
```

## Vercel Setup:

1. Connect your bot repo to Vercel
2. Go to Settings → Deploy
3. Set Start Command: `python bot.py`
4. Go to Variables tab and add:
   - `REDIS_URL` = `your-redis-url-here`
   - `TELEGRAM_BOT_TOKEN` = `your-bot-token-here`
   - `ADMIN_CHAT_ID` = `your-chat-id-here`
   - `PUBLIC_BASE_URL` = `https://your-domain.vercel.app`

5. Deploy!

## Check if it's working:

1. Check Vercel logs - should see "Bot is running..."
2. In Telegram, send `/start` to your bot
3. Bot should reply with commands list

