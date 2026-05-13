<div align="center">
  <h1>🤖 SAGOR BOT</h1>
  <p><b>A powerful Facebook Messenger Bot — AI chat, media downloader, group management, and a built-in Web Dashboard.</b></p>
  <img src="https://i.imgur.com/XLSPFgc.jpeg" alt="SAGOR BOT" width="400"/>
</div>

---

## 📊 STATS

<p align="center">
<img src="https://img.shields.io/badge/Commands-92-00d9ff?style=for-the-badge" />
<img src="https://img.shields.io/badge/Events-8-ff2d55?style=for-the-badge" />
<img src="https://img.shields.io/badge/Node.js-20.x-339933?style=for-the-badge&logo=node.js&logoColor=white" />
<img src="https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge" />
</p>

---

## ✨ FEATURES

- 🤖 **AI Chat** — Smart replies powered by OpenAI integration
- 🎬 **Video / Media Downloader** — TikTok, YouTube, Facebook, and more
- 🛡️ **Group Management** — Anti-out, Anti-name change, Welcome/Leave, Kick/Ban
- 🎨 **Stylish Image Cards** — Welcome cards, profile, rank built with Canvas + Jimp
- 🌍 **Multi-language** — English (default), and more
- 📊 **Web Dashboard** — Start/Stop/Restart bot, live stats, logs (port 5000)
- 🔁 **Auto-recovery** — Child process auto-restart with exponential backoff on crash
- 🍪 **Multi-cookie support** — Rotation across `cookie.txt`, `cookie2.txt`, `cookie3.txt`
- 💾 **SQLite Database** — Sequelize ORM, zero-config persistence

---

## 🚀 GETTING STARTED

### On Replit
1. Import this repo into Replit
2. Paste your Facebook appstate (cookie JSON) into `cookie.txt`
3. Add your Facebook UID to `ADMINBOT` and `NDH` arrays in `config.json`
4. Hit **Run** (workflow: `node index.js`)
5. Open the dashboard in the webview on port `5000`

### Local
```bash
npm install
node index.js
```

---
## Workflow
```
name: Node.js CI

on:
  workflow_dispatch:
  

jobs:
  build:


    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [16.x]
        # See supported Node.js release schedule at https://nodejs.org/en/about/releases/

    steps:
    - uses: actions/checkout@v2
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v2
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    - run: npm install
    - run: npm start
```


## 📁 PROJECT STRUCTURE

```
.
├── index.js                  # Entry point — Express dashboard + bot process manager
├── config.json               # All configuration (prefix, admins, features)
├── cookie.txt                # Facebook session (appstate JSON)
├── main/
│   ├── utils/sagor.js        # Bot core logic, config & module loader
│   ├── listen.js             # Central event listener
│   ├── controllers/          # DB controllers (Users, Threads, Currencies)
│   ├── database/             # Sequelize config + models
│   ├── handle/               # Command, reply, reaction, event handlers
│   ├── languages/            # Language files (en.lang, etc.)
│   └── index.html            # Dashboard UI
└── src/
    ├── commands/             # 92 command modules
    └── events/               # 8 event modules
```

---

## ⚙️ KEY CONFIG (config.json)

| Key | What it does |
|-----|--------------|
| `PREFIX` | Command prefix (default: `.`) |
| `ADMINBOT` | List of admin UIDs |
| `BOTNAME` | Bot display name |
| `language` | Language code (`en`, `vi`, etc.) |
| `dashBoard.port` | Dashboard port — must stay `5000` for Replit webview |
| `groupNoti.enable` | Welcome/Leave notifications |
| `botLogging.enable` | Bot add/kick logging |
| `twoIdMode` | Multi-cookie auto-switching |

---

## 🌐 WEB DASHBOARD

- **URL:** `http://0.0.0.0:5000`
- **Login:** `/login` (verify-code based)
- **Health check:** `/health`
- **Features:** Start/Stop/Restart bot, live stats, command list, log viewer

---

## 🛠️ TECH STACK

- **Node.js 20.x** — Runtime
- **Express.js** — Dashboard server
- **sagor-fca** — Facebook Chat API
- **Sequelize + SQLite** — Database
- **Socket.io** — Real-time uptime monitoring
- **canvas, jimp** — Image generation
- **openai** — AI chat features

---

## 🐛 TROUBLESHOOTING

| Issue | Fix |
|-------|------|
| Bot won't start, exit code `78` | All cookies expired — update `cookie.txt` |
| Dashboard not visible in webview | Set `config.json → dashBoard.port` to `5000` |
| Welcome message not sending | Set `groupNoti.enable: true` |
| Some commands fail (hack/uid/uptime) | Requires `libuuid` system dependency |

---

## 🔗 SOCIAL

<p align="center">
<a href="https://facebook.com/SAGOR.69x"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" /></a>
<a href="https://github.com/SAGOR-KINGx"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
<a href="https://wa.me/+8801611079915"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" /></a>
<a href="https://t.me/xxSaGorxx"><img src="https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" /></a>
</p>

---

## 📜 LICENSE

GPL-3.0 — © **SAGOR**

<div align="center">
  <sub>Built with 🩶 by SAGOR</sub>
</div>
