# LumenicData Careers Platform

Production-ready company website with integrated job application form that submits to Telegram.

## Setup

### 1. Environment Variables
Add to Vercel dashboard (Settings → Environment Variables):
```
TG_BOT_TOKEN=your_telegram_bot_token
TG_CHAT_ID=your_telegram_chat_id
```

### 2. Get Telegram Credentials
- **Bot Token:** Search `@BotFather` on Telegram, send `/newbot`
- **Chat ID:** Add bot to group, send message, visit `https://api.telegram.org/bot{TOKEN}/getUpdates`

### 3. Deploy
```bash
# Push to GitHub and import into Vercel
# or use Vercel CLI
vercel deploy
```

## Project Files

```
├── api/submit-application.js  # API endpoint (Vercel)
├── index.html                 # Landing page
├── about.html                 # About page
├── apply.html                 # Application form
├── main.js                    # Shared utilities
├── apply.js                   # Form handler
├── config.js                  # Client config
├── styles.css                 # Styling
├── package.json               # Dependencies
├── vercel.json                # Vercel config
└── README.md                  # This file
```

## API Endpoint

**POST /api/submit-application**

Sends form data and files to Telegram.

Request:
```json
{
  "formData": { "a-fullname": "Name", "a-email": "email@example.com" },
  "files": { "a-selfie": { "name": "file.jpg", "type": "image/jpeg", "data": "base64..." } }
}
```

Response:
```json
{ "success": true, "message": "Application submitted successfully" }
```

## Customization

- **Form Fields:** Edit `apply.html`
- **Colors:** Update CSS variables in `styles.css`
- **Telegram Message:** Modify `formatMessage()` in `api/submit-application.js`

## Troubleshooting

- **Form fails to submit:** Check environment variables in Vercel
- **Files don't upload:** Verify file size < 20MB
- **No Telegram message:** Confirm bot token and chat ID are correct
- **Browser console errors:** Look for `[v0-SUBMISSION]` logs
- **Server errors:** Check Vercel function logs with `[API]` prefix

## Stack

- Frontend: HTML5, CSS3, Vanilla JavaScript
- Backend: Node.js (Vercel Functions)
- Integration: Telegram Bot API
- Hosting: Vercel
