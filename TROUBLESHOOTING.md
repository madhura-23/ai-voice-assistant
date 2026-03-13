# 🆘 Voice Assistant - Troubleshooting Guide

If the "Start Recording" button doesn't work, follow this guide to diagnose the issue.

---

## ⚡ Quick Fix (Try This First!)

### 1. **Check Your Browser**
- ✅ **Works best with**: Chrome, Edge, Safari
- ❌ **May not work with**: Firefox (partial), Internet Explorer (old)

**Solution**: Use **Chrome** or **Edge** for best results

### 2. **Allow Microphone Permission**
When you first click "Start Recording", your browser should ask for microphone access.

**Steps:**
1. Click "Start Recording" 
2. Look for a notification asking about microphone access
3. Click "Allow" or "Yes"
4. Try recording again

**Still not seeing it?**
- **Chrome/Edge**: Click the 🔒 icon in address bar → Microphone → Allow
- **Safari**: Settings → Websites → Microphone → Allow
- **Firefox**: About:preferences → Privacy → Permissions → Microphone → Allow

### 3. **Refresh the Page**
```
Press: Ctrl+R (Windows) or Cmd+R (Mac)
```

---

## 🔍 Use the Diagnostics Page

I've created a **diagnostic tool** to identify exactly what's wrong!

### Access It:
1. Upload `diagnostics.html` to your GitHub repo (same as index.html)
2. Visit: `https://yourusername.github.io/ai-voice-assistant/diagnostics.html`
3. OR directly open the `diagnostics.html` file in your browser

### What It Does:
- ✅ Checks browser compatibility
- ✅ Tests microphone access
- ✅ Tests Web Speech API
- ✅ Tests speaker/audio output
- ✅ Shows detailed error messages

### Follow the Tests:
1. **Browser Support** - Shows if your browser is compatible
2. **Click "Request Microphone Permission"** - Tests mic access
3. **Click "Test Speech Recognition"** - Try speaking
4. **Click "Test Speaker"** - Hear "Hello" message

Each test will show ✅ (working) or ❌ (not working)

---

## Common Issues & Solutions

### ❌ "Start Recording" Button Doesn't Respond

**Cause**: Browser doesn't support Web Speech API

**Solution**:
- Use Chrome, Edge, or Safari instead
- Check diagnostics page - should show ❌ for Web Speech API
- Firefox doesn't support it yet

---

### ❌ Microphone Permission Denied

**Cause**: Browser permission not granted

**Solution 1 - Allow Permission:**
1. Browser should ask when you click "Start Recording"
2. Click "Allow" or "Yes"
3. Refresh page and try again

**Solution 2 - Reset Permissions:**
- **Chrome**: Settings → Privacy → Microphone → Clear all sites → Reload
- **Safari**: Settings → Websites → Microphone → Your site → Allow
- **Edge**: Settings → Privacy → App permissions → Microphone → Allow

**Solution 3 - Check System Permissions:**
- Windows: Settings → Privacy & security → Microphone → Allow apps
- Mac: System Preferences → Security & Privacy → Microphone → Allow

---

### ❌ "No speech detected" Error

**Cause**: Microphone not picking up sound

**Solutions:**
1. **Speak louder** - Microphone is sensitive
2. **Reduce background noise** - Go to quieter place
3. **Speak after clicking button** - Wait for "Recording..." to appear
4. **Check microphone works** - Try Zoom, Teams, or other voice app
5. **Try different browser** - Chrome usually works best

---

### ❌ "Not allowed" Error

**Cause**: Browser can't access microphone

**Solutions:**
1. Check browser permissions (see above)
2. Check computer settings for app permissions
3. Restart browser completely
4. Try in an Incognito/Private window

---

### ❌ No Sound Output (Can't Hear Responses)

**Cause**: Speaker issue or browser permissions

**Solutions:**
1. **Check volume**: 
   - Windows: Check speaker icon in taskbar
   - Mac: Check volume in menu bar
   - Browser: Unmute tab (right-click tab)

2. **Check browser permissions**:
   - Chrome: Settings → Privacy → Microphone → Allow (also grants audio output)

3. **Test speakers**:
   - Visit YouTube and play a video
   - If sound works, it's a speech synthesis issue

4. **Use diagnostics**:
   - Click "Test Speaker" on diagnostics page
   - Should say "Hello, the voice assistant is working!"

---

### ❌ API Key Error

**Cause**: Invalid or missing API key

**Solutions:**
1. Check your API key at https://console.anthropic.com/account/keys
2. Make sure you copied the ENTIRE key
3. Try pasting again slowly
4. Make sure key starts with `sk-ant-`
5. Check that your Anthropic account has API access enabled

---

### ❌ Network Error When Sending Message

**Cause**: API request failed

**Solutions:**
1. Check internet connection
2. Verify API key is correct
3. Wait a moment and try again
4. Check https://status.anthropic.com for outages

---

### ❌ Page Loads But Nothing Works

**Cause**: JavaScript not running

**Solutions:**
1. Refresh page (Ctrl+R or Cmd+R)
2. Clear browser cache
   - Chrome: Ctrl+Shift+Delete, Clear cache
3. Try Incognito/Private window
4. Update your browser to latest version
5. Check browser console for errors (F12 → Console tab)

---

## 🔧 Advanced Troubleshooting

### Check Browser Console for Errors

1. **Open Developer Tools**: Press `F12` or `Ctrl+Shift+I`
2. Click **"Console"** tab
3. Look for red error messages
4. Screenshot and share the error

### Enable Logging

The new version of index.html has better logging. You should see messages like:
```
[Voice Assistant] Web Speech API is supported
[Voice Assistant] Speech Recognition initialized
[Voice Assistant] Recording started
```

If you see errors, share them in the console.

---

## 📱 Mobile Troubleshooting

### iPhone/iPad (Safari)
1. Go to Settings → Safari → Microphone → Allow
2. Reload page
3. Click microphone button
4. Allow microphone access when asked

### Android (Chrome)
1. Open Chrome settings
2. Site settings → Microphone → Allow
3. Reload page
4. Try again

**Note**: Mobile browsers have better support now, but desktop Chrome is most reliable.

---

## ✅ Verification Checklist

Before asking for help, check all of these:

- [ ] Using Chrome, Edge, or Safari (not Firefox)
- [ ] Ran diagnostics.html - all tests show ✅
- [ ] Allowed microphone permission in browser
- [ ] Allowed microphone permission in OS settings
- [ ] Checked microphone works in other apps (Zoom, Teams, etc.)
- [ ] Entered valid Claude API key
- [ ] Page is fully loaded (wait 3 seconds)
- [ ] Refreshed page after API key entry
- [ ] Speaking clearly after clicking "Start Recording"

---

## 🆘 Still Not Working?

### If nothing works after trying all above:

1. **Take a screenshot** of:
   - Your browser address bar
   - The error message (if any)
   - The diagnostics page results

2. **Open browser console** (F12):
   - Go to Console tab
   - Screenshot all error messages

3. **Share these details**:
   - Which browser and version?
   - Which operating system?
   - What happens when you click "Start Recording"?
   - What does diagnostics page show?

### Get Help:
- Check [Claude API Docs](https://docs.claude.com)
- Try a different browser
- Try on a different device
- Check GitHub Issues on the repository

---

## 🎯 Optimal Setup

For the **best experience**:

1. **Use Google Chrome** on Desktop
2. **High-quality microphone** (or at least test mic)
3. **Quiet environment** (minimal background noise)
4. **Good internet connection** (broadband)
5. **Recent browser version** (updated within last month)

---

## 💡 Pro Tips

- **Speak naturally** - Don't shout or whisper
- **Pause for responses** - Let AI finish speaking before interrupting
- **Test first** - Use diagnostics page before assuming it's broken
- **Check logs** - Browser console (F12) often shows the real error
- **Restart browser** - Fixes many issues
- **Try Incognito** - Disables extensions that might interfere

---

## 📞 Still Need Help?

1. Fill out the checklist above ✅
2. Run diagnostics.html and check results
3. Look at browser console (F12) for errors
4. Share your findings in a GitHub Issue

The diagnostics page will usually pinpoint exactly what's wrong!

---

**Last resort**: Create a GitHub issue with:
- Browser + version
- Operating system
- Screenshot of diagnostics results
- Screenshot of console errors
- What you tried to fix it

Good luck! 🚀
