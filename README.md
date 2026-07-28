📱 K2_RAT - Complete Documentation

⚠️ DISCLAIMER

This tool is for educational and authorized security testing purposes ONLY. Unauthorized access to devices is illegal. Use only on devices you own or have explicit written permission to test. The creators assume NO responsibility for misuse.

---

📱 Overview

K2_RAT is a powerful C2 (Command & Control) server for Android device management and security testing. It provides comprehensive remote monitoring and control capabilities through an intuitive Telegram bot interface.

🌟 Key Features

Category Features
Device Management View connected devices, models, IPs, versions, connection status
File System Full file explorer with navigation, download, delete, create folder
Telecommunications Access contacts, read/send SMS, view call logs
Media Capture Main/selfie camera, video recording, audio recording
Location Services GPS coordinates, Google Maps integration
Device Control Silent/vibrate/normal modes, hide/unhide app, lock device
Security Keylogger, clipboard control, notifications
WebViews Fake and overlay webviews with custom URLs

---

🚀 Quick Start Guide

📋 Prerequisites

· Node.js v14 or higher
· Telegram Bot Token (from @BotFather)
· Telegram Chat ID (your personal or group ID)
· Target Android device with K2_RAT client app installed

🔧 Installation

```bash
# Clone repository
git clone https://github.com/yourusername/k2_rat.git
cd k2_rat

# Install dependencies
npm install express socket.io node-telegram-bot-api multer

# Configure settings
# Create data.json file (see configuration section)

# Start server
node server.js
```

⚙️ Configuration (data.json)

```json
{
  "token": "YOUR_TELEGRAM_BOT_TOKEN",
  "id": "YOUR_TELEGRAM_CHAT_ID",
  "url": "https://your-server.com"
}
```

Get Telegram Bot Token: Talk to @BotFather on Telegram

---

🎮 Telegram Bot Interface

📸 Main Interface

images/functions.png
Figure 1: K2_RAT Telegram Bot Main Interface

🎯 Target Device Selection

images/targetappscree.png
Figure 2: Device Selection and Available Actions

📋 Main Menu Options

```
┌─────────────────────────────────────┐
│  ✯ Devices ✯    ✯ All ✯           │
│  ✯ About us ✯                      │
└─────────────────────────────────────┘
```

🎯 Device Selection Menu

When you select ✯ Devices ✯, you'll see:

```
📱 Device List
Device Count: 2

Device 1
device → Samsung-Galaxy-S21
model → SM-G991B
ip → 192.168.1.100
version → 1.0.0

Device 2
device → Google-Pixel-6
model → Pixel 6
ip → 192.168.1.101
version → 1.0.0
```

📱 Device Action Menu

After selecting a specific device, you get access to all available commands:

```
┌──────────────────────────────────────────────────────┐
│ ✯ Contacts ✯      ✯ SMS ✯                         │
│ ✯ Calls ✯         ✯ Gallery ✯                     │
│ ✯ Main Camera ✯   ✯ Selfie Camera ✯               │
│ 🔇 Silent Mode    📳 Vibrate Mode                  │
│ 🔊 Normal Mode    🔄 Toggle Silent                 │
│ ✯ Microphone ✯    ✯ Clipboard ✯                   │
│ ✯ Toast ✯         ✯ Pop Notification ✯            │
│ ✯ Keylogger ON ✯  ✯ Keylogger OFF ✯               │
│ ✯ File Explorer ✯ 📁 Create Folder                 │
│ 🔒 Hide App       🔓 Unhide App                    │
│ 📍 Get Location   🗺️ Location Map                  │
│ 🔊 Play Audio     📱 Installed Apps                │
│ 📱 Device Info    📞 Call Number                   │
│ 🌐 Show Fake WV   🌐 Hide Fake WV                  │
│ 🌐 Set WV URL     🌐 Get WV URL                    │
│ 🌐 Show Overlay   🌐 Hide Overlay                  │
│ 🌐 Set Overlay URL                                 │
│ 🔒 Lock Device    ✯ Soft Encrypt ✯                │
│ ✯ Send SMS ✯     ✯ Video ✯                       │
│ ✯ Send SMS to All                                  │
│ 📁 DCIM           📁 Pictures                      │
│ 📁 Downloads      📁 Root                          │
│ ✯ Back to main menu ✯                             │
└──────────────────────────────────────────────────────┘
```

---

📂 File Explorer Guide

🗂️ Navigation Interface

The file explorer provides an interactive folder browsing experience:

```
📁 /storage/emulated/0/

📊 245 items (Page 1 of 13)
📁 12 folders
📄 233 files

📌 Folders = 📁  |  Files = 📄🖼️🎬

┌────────────┬────────────┐
│ 📁 DCIM   │ 📁 Pictures │
│ 📁 Music  │ 📁 Downloads│
│ 📁 Videos │ 📁 Documents│
├────────────┼────────────┤
│ 📄 report │ 📄 note.txt │
│ 🖼️ photo1 │ 🎬 video.mp4│
├────────────┼────────────┤
│ ⬅️ Prev   │ Next ➡️    │
│ ⬅️ Back   │ ↻ Refresh   │
│ 📁 Create Folder       │
│ 🏠 Main Menu            │
└─────────────────────────┘
```

🔽 File Actions

Tapping a file opens action menu:

```
📄 File: secret_document.pdf

📌 Size: 2.4 MB
📌 Type: pdf
📌 Path: /storage/emulated/0/Documents/secret_document.pdf

📌 Choose an action:

┌────────────┬────────────┐
│ 📤 Download│ 🗑️ Delete │
├────────────┼────────────┤
│ 📋 Info    │            │
├────────────┼────────────┤
│ ⬅️ Back    │            │
└────────────┴────────────┘
```

---

📞 Call & SMS Features

📱 Call Number Workflow

1. Select a target device
2. Choose 📞 Call Number
3. If 1 SIM detected: Enter phone number directly
4. If 2+ SIMs detected: Select SIM card → Enter phone number
5. Device initiates call

```
📌 Selected: [SIM Name] (SIM 2)

📝 Format: 0999999999
```

📨 Send SMS Workflow

1. Select target device
2. Choose ✯ Send SMS ✯
3. Select SIM (if multiple)
4. Enter phone number
5. Enter message text
6. SMS is sent from target device

📤 Send SMS to All Contacts

· Sends a single message to ALL contacts on the device
· Use with extreme caution
· Will send from default SIM

---

🔐 Security Features

🔒 Lock Device

Locks the target device immediately with custom message:

```
🔒 Lock Device

🔐 This will IMMEDIATELY lock the device.
📝 Enter custom lock message (or send default)

📌 Default: "Your device is locked! Contact Admin."

[Your device is locked! Contact Admin @Grey_Carter]
[⚠️ Device Locked! Contact support.]
[✯ Back to main menu ✯]
```

✯ Soft Encrypt

Encrypt files or text (device remains functional):

```
✯ Soft Encrypt (File Only)

📁 Enter file path OR text to encrypt.
🔑 Default key: MySecretKey12345
📝 Format: file_path_or_text|YourKey
⚠️ Device will NOT be locked.

Example:
/storage/emulated/0/DCIM/secret.txt|MyKey123
Hello World|MySecretKey12345
```

---

🌐 WebView Features

Fake WebView

Displays a webview that looks like a legitimate app:

```
🌐 Show Fake WebView     → Shows webview
🌐 Hide Fake WebView     → Hides webview  
🌐 Set Fake WebView URL  → Change URL
🌐 Get Fake WebView URL  → Get current URL
```

Overlay WebView

Displays a webview on top of other apps:

```
🌐 Show Overlay WebView    → Shows overlay
🌐 Hide Overlay WebView    → Hides overlay
🌐 Set Overlay WebView URL → Change URL
```

---

🎥 Media Features

📸 Camera

Command Function
✯ Main Camera ✯ Capture from rear camera
✯ Selfie Camera ✯ Capture from front camera

🎬 Video Recording

1. Choose ✯ Video ✯
2. Select camera (Back/Front)
3. Select quality (Low/Medium/High)
4. Enter duration (seconds)
5. Video is sent to Telegram

🎤 Microphone Recording

1. Choose ✯ Microphone ✯
2. Enter duration (seconds)
3. Audio file sent to Telegram

---

📊 Command Reference Table

Command Description Output
✯ Contacts ✯ Get contact list Text file with contacts
✯ SMS ✯ Get SMS messages Text file with messages
✯ Calls ✯ Get call logs Text file with call history
✯ Gallery ✯ Browse images Interactive gallery
✯ Main Camera ✯ Capture photo Image file
✯ Selfie Camera ✯ Capture selfie Image file
✯ Video ✯ Record video Video file
✯ Microphone ✯ Record audio Audio file
📍 Get Location Get GPS location Coordinates and address
🗺️ Location Map Open in Maps Google Maps link
📱 Device Info Get device details System information
📱 Installed Apps List all apps Text file with app list
✯ File Explorer ✯ Browse files Interactive browser
✯ Keylogger ON ✯ Start keylogging Logs keys
✯ Keylogger OFF ✯ Stop keylogging -
🔒 Hide App Hide from launcher App hidden
🔓 Unhide App Show in launcher App visible
🔒 Lock Device Lock screen Device locked
✯ Soft Encrypt ✯ Encrypt file/text Encrypted output
✯ Send SMS ✯ Send SMS SMS sent
✯ Send SMS to All ✯ Mass SMS SMS sent to all

---

🔧 Troubleshooting Guide

❌ Device Not Connecting

Issue Solution
Client can't reach server Check server URL in client app
Firewall blocking Open port 3000 (or configured port)
Network issues Ensure both devices have internet access
Server not running Run node server.js

❌ Files Not Downloading

Issue Solution
Permission denied Check file permissions on Android
File doesn't exist Verify path is correct
Path too long Navigate to directory first

❌ Telegram Bot Not Responding

Issue Solution
Invalid token Get new token from @BotFather
Wrong chat ID Use @userinfobot to get ID
Bot not in chat Add bot to group/channel

---

📁 Project Structure

```
k2_rat/
├── server.js              # Main C2 server (core logic)
├── data.json              # Configuration file
├── package.json           # Node.js dependencies
├── received/              # Downloaded files directory
├── images/                # Documentation images
│   ├── functions.png      # Main interface screenshot
│   └── targetappscree.png # Device selection screenshot
└── README.md              # This documentation
```

---

📦 Dependencies

```json
{
  "express": "^4.18.2",
  "socket.io": "^4.6.1",
  "node-telegram-bot-api": "^0.61.0",
  "multer": "^1.4.5-lts.1"
}
```

---

🛡️ Security Best Practices

1. ✅ DO
   · Use HTTPS in production
   · Change default credentials
   · Restrict bot access
   · Keep server updated
   · Log all activities
2. ❌ DON'T
   · Share server details publicly
   · Use on unauthorized devices
   · Ignore error logs
   · Skip security updates

---

⚡ Performance Tips

1. Use pm2 for process management:

```bash
npm install -g pm2
pm2 start server.js --name k2_rat
```

2. Monitor server health:

```bash
pm2 logs k2_rat
pm2 monit
```

3. Configure for production:

```bash
# Use environment variables
export PORT=3000
node server.js
```

---

📝 License & Legal

This software is provided for EDUCATIONAL PURPOSES ONLY.

· Unauthorized device access is illegal
· Users are responsible for compliance with local laws
· Use only with explicit consent
· Not responsible for misuse

---

🤝 Support & Contact

Contact Information
Telegram @k2takeNgo
Admin @Grey_Carter
Issues GitHub Issues

---

🔄 Version History

Version Features
1.0 Initial release - Full C2 functionality

---

📚 Additional Resources

· Socket.IO Documentation
· Telegram Bot API
· Node.js Documentation

---

⚠️ Final Warning

Remember: This tool is powerful and potentially dangerous. Use responsibly. Unauthorized access to devices is a serious crime in most jurisdictions. Always obtain proper authorization before testing.

---

Last Updated: 2026

---
