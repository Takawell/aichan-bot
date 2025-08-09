# ⚡ AICHAN DISCORD BOT  
### 🧨 Distributed Web Attack Toolkit Controlled via Discord (Python + Node.js)

**AICHAN** is a modular, high-performance web stress toolkit operated remotely via Discord. It acts as a command hub for launching advanced HTTP flood methods using Node.js-based executors — all triggered securely from Discord in real time.

---

## 🧠 Key Features

- 🧬 Remote-controlled via Discord bot
- 🔥 Supports multiple HTTP flood methods
- 🌍 Proxy-enabled (via `proxies.txt`)
- ⚙️ Combines Python (control) & JavaScript (execution)
- 🛡️ Access-restricted via user ID
- 🧩 Plug-and-play architecture — just drop your method scripts in

---

## 📁 Project Structure

```
📦 AICHAN/
├── bot.py               # Main Discord controller
├── config.json          # Bot token + room ID
├── setup.py             # Python dependencies
├── node_modules.zip     # Node.js dependencies (prepackaged)
├── proxies.txt          # Proxy list (used by JS methods)
├── package.json         # Node project metadata
├── *.js                 # Attack modules (see below)
```

### 🚀 Available Methods (JavaScript Modules)

- `HTTP-RAND.js` – Randomized HTTP flooding with rotation
- `HTTP-RAW.js` – Raw packet HTTP flooder
- `HTTP-SOCKETS.js` – Low-level socket-based attack
- `cf.js` – Basic Cloudflare bypassing logic
- `slow.js` – Slowloris-style connection hold
- `hyper.js`, `io-stresser.js`, `ll.js`, `bypasserr.js` – Auxiliary methods for variation & scale

> Modules auto-execute via `bot.py` using system calls.  
> Proxy support is built-in (from `proxies.txt`).

---

## ⚙️ Installation & Setup

### 1. Extract Node.js Dependencies
```bash
unzip node_modules.zip
```

### 2. Install Node.js
Download from: [https://nodejs.org](https://nodejs.org)

### 3. Configure the Bot

Edit `config.json`:
```json
{
  "token": "YOUR_DISCORD_BOT_TOKEN",
  "roomID": "DISCORD_CHANNEL_ID"
}
```

In `bot.py`, set your authorized Discord user ID:
```python
AUTHORIZED_USER_ID = 123456789012345678
```

### 4. Install Python Requirements
```bash
python setup.py install
```

Or install manually:
```bash
pip install discord requests
```

### 5. Launch the Bot
```bash
python bot.py
```

---

## 🧨 Command Format (via Discord)

In your Discord server (inside the configured channel), use:

```
!attack <method> <target> <duration>
```

Example:
```
!attack HTTP-RAND https://example.com 60
```

💡 Bot will invoke the matching JS script with the target and duration parameters.

---

## 🛡️ Access Control

Only the `AUTHORIZED_USER_ID` defined in `bot.py` can execute commands.  
Messages from others are ignored for operational security.

---

## ⚠️ Legal Notice

This tool is provided **as-is** for **educational and authorized testing** only.  
Any misuse is your responsibility.  
Use it ethically. Or face the consequences.

---

## 👑 Credits

Built for those who understand control at scale.  
When silence is too loud, **AICHAN speaks with traffic.**

---

