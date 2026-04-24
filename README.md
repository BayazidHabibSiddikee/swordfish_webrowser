<div align="center">

```
 ███████╗██╗    ██╗ ██████╗ ██████╗ ██████╗ ███████╗██╗███████╗██╗  ██╗
 ██╔════╝██║    ██║██╔═══██╗██╔══██╗██╔══██╗██╔════╝██║██╔════╝██║  ██║
 ███████╗██║ █╗ ██║██║   ██║██████╔╝██║  ██║█████╗  ██║███████╗███████║
 ╚════██║██║███╗██║██║   ██║██╔══██╗██║  ██║██╔══╝  ██║╚════██║██╔══██║
 ███████║╚███╔███╔╝╚██████╔╝██║  ██║██████╔╝██║     ██║███████║██║  ██║
 ╚══════╝ ╚══╝╚══╝  ╚═════╝ ╚═╝  ╚═╝╚═════╝ ╚═╝     ╚═╝╚══════╝╚═╝  ╚═╝
```

**A minimal, privacy-first browser with built-in AVR toolchain — built from scratch in Python.**

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![PySide6](https://img.shields.io/badge/PySide6-6.5+-41CD52?style=flat-square&logo=qt&logoColor=white)](https://pypi.org/project/PySide6/)
[![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20Windows%20%7C%20Android-lightgrey?style=flat-square)](.)
[![License](https://img.shields.io/badge/License-Open%20Source-blue?style=flat-square)](.)

</div>

---

## What is SwordFish?

SwordFish started as a learning project — a raw Python socket server serving HTML pages — and grew into a full browser + AVR microcontroller control plane. It runs your own local web server, renders pages in a Qt-based browser, and lets you compile and flash AVR chips (ATmega8, ATmega328P, ATmega32) directly from a web UI.

---

## Features

| Feature | Details |
|---|---|
| 🔒 **Privacy-first** | Persistent profile stored locally, no external tracking |
| 📺 **Media downloader** | Video (144p → 4K) and audio (MP3/M4A/OGG) via `yt-dlp` |
| 🚫 **Ad blocker** | CSS-selector based, runs on every page |
| 🔖 **Bookmarks & History** | Saved to `~/.config/SwordFish/data.json` |
| 🌐 **Cross-platform** | Linux, Windows, Android (Termux) |
| 🔧 **Raw terminal** | Run shell commands from the browser tab |
| 🇺🇸 **English locked** | Forces English on all pages regardless of system locale |

---

## Project Structure

```
swordfish/
├── main.py           ← Entry point: starts server + opens browser window
│
├── requirements.txt  ← pip packages only
├── requirements.sh   ← Full setup script (Linux / Android)
├── requirements.bat  ← Full setup script (Windows)
│
├── swordfish.sh      ← Linux launcher script
├── swordfish.desktop ← Linux app shortcut (.desktop entry)
│
└── dist/
    └── SwordFish.exe ← Pre-built Windows executable
```

---

## Installation

### Linux / Fedora (recommended)

```bash
# Clone the repo
git clone https://github.com/BayazidHabibSiddikee/swordfish_webrowser.git
cd swordfish_webrowser

# Run the setup script — handles everything automatically
chmod +x requirements.sh
./requirements.sh
```

The script auto-detects your distro and installs:
- `ffmpeg` via `dnf` / `apt` / `pacman`
- `PySide6` and `yt-dlp` via pip
- The app shortcut in your launcher (search **SwordFish**)

Then run:
```bash
python main.py
```

---

### Windows

```bat
git clone https://github.com/BayazidHabibSiddikee/swordfish_webrowser.git
cd swordfish_webrowser
requirements.bat
```

Or just download and run `dist/SwordFish.exe` — no Python needed.

---

### Android (Termux)

```bash
pkg install git python
git clone https://github.com/BayazidHabibSiddikee/swordfish_webrowser.git
cd swordfish_webrowser
chmod +x requirements.sh && ./requirements.sh
python server.py   # GUI not available on Android — server + AVR tools work fine
```

---

## Install as a Real App on Linux

After running `requirements.sh` this is done automatically, but if you want to do it manually:

```bash
# 1. Make the launcher executable
chmod +x swordfish.sh

# 2. Edit paths inside swordfish.desktop to match your folder
nano swordfish.desktop

# 3. Copy to the applications folder
cp swordfish.desktop ~/.local/share/applications/

# 4. Refresh the launcher database
update-desktop-database ~/.local/share/applications/
```

Search **SwordFish** in GNOME / KDE / XFCE — it will appear with its icon.
You can right-click → **Pin to Dock** from there.

---

The terminal section below lets you run any shell command from the browser.


---

## Data & Settings

All user data is stored **locally** — nothing is sent anywhere.

| Data | Location |
|---|---|
| Bookmarks & History | `~/.config/SwordFish/data.json` |
| Browser settings | `~/.config/SwordFish/Browser.conf` |
| Cookies & Cache | `~/.config/SwordFish/browser_profile/` |
| Windows Registry | `HKCU\Software\SwordFish\Browser` |

---

## Built With

- [PySide6](https://pypi.org/project/PySide6/) — Qt6 Python bindings
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) — media downloader
- Python standard library only for the HTTP server (`socket`, `subprocess`, `threading`)
- AVR toolchain — `avr-gcc`, `avr-objcopy`, `avrdude`

---

<div align="center">

Built by [@BayazidHabibSiddikee](https://github.com/BayazidHabibSiddikee) — learning by building.

</div>
