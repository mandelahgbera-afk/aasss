# Application Form API - Setup Required

## Critical: Required Environment Variables

Your application form REQUIRES the following Telegram bot credentials to function:

### Required Environment Variables:
```
TG_BOT_TOKEN=your_bot_token_here
TG_CHAT_ID=your_chat_id_here
```

## What Happens Without These Variables

If `TG_BOT_TOKEN` or `TG_CHAT_ID` are missing:

1. **API Returns HTTP 503 (Service Unavailable)**
2. **User Sees Error Message**: "Application backend is not properly configured. Please contact the administrator."
3. **Form Data is NOT Submitted** (nothing is lost, user can retry)
4. **Server Logs**: "[API] FATAL: Telegram credentials not configured. Rejecting submission."

## No Silent Failures

The API WILL NOT:
- Accept submissions without credentials
- Silently drop form data
- Pretend submissions succeeded
- Store data anywhere else as fallback

## Setting Up Telegram Bot Credentials

1. Create a Telegram bot via [@BotFather](https://t.me/botfather)
2. Get your Chat ID by messaging the bot and checking updates
3. Add to Vercel project environment variables:
   - Go to Project Settings → Environment Variables
   - Add: `TG_BOT_TOKEN` and `TG_CHAT_ID`
   - Redeploy

## Testing the API

Once credentials are set, the form will:
- ✓ Send application data to Telegram
- ✓ Upload all files (selfie, ID photos, resume)
- ✓ Show success message to user
- ✓ Display success state page

## Error Handling

All errors are communicated clearly to users:
- Missing credentials → 503 error
- Network issues → User-friendly message
- File too large → Clear size limit message
- Invalid data → Specific validation errors

**Status**: Configuration required before deployment
