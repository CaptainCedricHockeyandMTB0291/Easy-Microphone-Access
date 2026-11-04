# 🎙️ Safari Microphone Launcher
An easy bookmarklet to activate your microphone on your iPad or mobile device if it doesn’t allow you to. While it’s not tested it might work on windows laptop and pc, and it should work on Mac OS. A lightweight JavaScript bookmarklet that allows users to activate their device's microphone directly from their browser.

## ✨ Features

- 🎙️ **One-Click Activation** – Request microphone access with a single click.
- 🔐 **Permission-Based** – Uses the browser's built-in microphone permission system.
- 🔔 **Activation Notification** – Displays a confirmation message when microphone access is granted.
- ⚠️ **Error Handling** – Notifies users if microphone access is unavailable or denied.
- 📡 **Stream Storage** – Temporarily stores the microphone stream in `window._micStream`.

## 💻 Installation

1. Open Safari or another compatible browser.
2. Create a new bookmark.
3. Name it **Microphone Launcher**.
4. Edit the bookmark's URL.
5. Replace the existing URL with the JavaScript code below.
6. Save your bookmark.

## 🚀 Code

```javascript
javascript:(async()=>{try{const s=await navigator.mediaDevices.getUserMedia({audio:true});alert("🎙️ Microphone is ON!");window._micStream=s}catch(e){alert("Microphone unavailable: "+e.message)}})();
```

## 🔒 Privacy & Permissions

- The bookmarklet requests microphone access through the browser's native permission prompt.
- It does not transmit or upload audio.
- The microphone stream remains available in the current page through `window._micStream`.
- Microphone access requires user permission and a secure browser context (HTTPS or localhost).

**Important:** The microphone remains active until its audio tracks are stopped or the page is closed.

To stop the microphone manually, run:

```javascript
window._micStream?.getTracks().forEach(track => track.stop());
```

## 🌐 Compatibility

Designed for browsers that support:
- JavaScript bookmarklets
- `navigator.mediaDevices.getUserMedia()`
- Audio media streams

## 📜 License

MIT License (or choose another license for your project).

---

**Made for simple, accessible microphone activation directly from your browser.** 🎙️
