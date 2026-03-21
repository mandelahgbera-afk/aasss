# LumenicData Application Form

Professional multi-step recruitment form with complete validation, file uploads, and error handling.

## Features

- **Multi-step Navigation** - 4-step form with progress tracking
- **Form Validation** - Real-time validation for email, phone, SSN, URLs, etc.
- **File Uploads** - Drag & drop, file size validation (4MB max per file)
- **Telegram Integration** - Automatic submission to Telegram with files
- **Error Recovery** - Failed submissions saved locally for recovery
- **Offline Detection** - Detects network status and notifies users
- **Cross-browser** - Works on all modern browsers (Chrome, Firefox, Safari, Edge)
- **Mobile Optimized** - Fully responsive design

## Deployment

Set environment variables on Vercel:
- `TG_BOT_TOKEN` - Your Telegram bot token
- `TG_CHAT_ID` - Target Telegram chat ID

## File Structure

```
├── apply.html          # Main form markup
├── apply.js            # Form logic & validation (850 lines, optimized)
├── api/
│   └── submit-application.js  # Backend API handler
├── styles.css          # Form styling
├── index.html          # Homepage
├── about.html          # About page
├── config.js           # Configuration
├── main.js             # Global script
└── package.json        # Dependencies
```

## Code Quality

✓ No unnecessary logging
✓ Production-ready error handling
✓ Comprehensive validation
✓ Memory-efficient DOM manipulation
✓ Cross-browser compatible
✓ ARIA accessible

---

**Status**: ✅ Production Ready
