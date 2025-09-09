# Google Ads Tag Troubleshooting Guide

## Current Status
❌ Google Tag Assistant reports: "Your Google tag wasn't detected on 'pcspetshipper.com'"

## What We've Fixed
✅ Simplified Google Ads implementation on all HTML pages  
✅ Added Netlify configuration files (_headers)  
✅ Created verification tools  
✅ Removed complex debugging code that might interfere  

## How to Test the Fix

### Step 1: Use Simple Test Page
1. Go to: `https://pcspetshipper.com/google-ads-simple.html`
2. Open Google Tag Assistant 
3. Test this page - it should detect the Google Ads tag
4. If ✅ detected, the simplified code works

### Step 2: Test Main Pages
After confirming the simple page works:
1. Test `https://pcspetshipper.com/` (homepage)
2. Test `https://pcspetshipper.com/book-transport.html`
3. All pages should now detect the tag

### Step 3: Alternative Testing Methods
If Google Tag Assistant still fails:

**Method 1: Browser Developer Tools**
1. Press F12 to open Developer Tools
2. Go to Console tab
3. Look for Google Analytics/gtag messages
4. Type: `window.gtag` - should show function, not undefined

**Method 2: Network Tab**
1. Press F12, go to Network tab
2. Reload page
3. Search for "googletagmanager.com"
4. Should see the gtag.js file loading

## Current Google Ads Code
All pages now use this simplified implementation:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=AW-17538330823"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'AW-17538330823');
</script>
```

## If Tag Still Not Detected

### Possible Issues:
1. **Ad Blocker** - Disable temporarily for testing
2. **Browser Extensions** - Try incognito/private mode
3. **Network/Firewall** - Corporate networks might block
4. **Cache** - Hard refresh (Ctrl+F5) or clear browser cache
5. **Netlify Deployment** - Wait 5-10 minutes after GitHub push

### Next Steps:
1. Push these changes to GitHub
2. Wait for Netlify auto-deployment (5-10 minutes)
3. Test the simple page first: `/google-ads-simple.html`
4. Clear browser cache and test in incognito mode
5. If still failing, try different browser/network

## Verification Pages Created:
- `/google-ads-simple.html` - Basic test page
- `/verify-ads.html` - Advanced verification with debugging tools

## Account Details:
- **Google Ads ID**: AW-17538330823
- **Domain**: pcspetshipper.com
- **Implementation**: Simplified gtag.js (most compatible)

---
**Note**: Google Ads data may take 24-48 hours to appear in your account even if the tag is working correctly.