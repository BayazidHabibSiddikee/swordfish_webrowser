# 🐟 SwordFish Browser

SwordFish is a simple, minimal, and privacy-focused web browser designed for users who want a clean browsing experience without tracking or bloat.

## 🚀 Key Features

- **Privacy-First**: No tracking of user data.
- **Zero Bloat**: No personal settings, no persistent cache, and no complex configurations.
- **Built-in Media Downloader**: Integrated support for downloading videos and audio from the web using `yt-dlp`.
- **Minimalist UI**: A clean interface with essential navigation controls.
- **Basic Ad-Blocking**: Includes a lightweight script to hide common ad selectors.
- **Cross-Platform**: Works on Windows, Linux, macOS, and Android (via Termux).

## 🛠️ Installation & Setup

### Prerequisites

The browser is built using **PySide6**. You will need Python installed on your system.

1. **Install Dependencies**:
   ```bash
   pip install PySide6
   ```

2. **Optional: For Media Downloads**:
   To enable the video and audio download features, install `yt-dlp`:
   ```bash
   pip install yt-dlp
   ```
   *Note: The browser will fallback to `curl` (Windows) or `wget` (Linux/macOS) if `yt-dlp` is not found.*

### Running the Browser

Navigate to the project folder and run:
```bash
python src/main.py
```

## 📂 Project Structure

- `src/main.py`: The core application logic, including the UI setup, navigation, and download handlers.
- `requirements.txt`: List of required Python packages.

## 🔧 Customization

SwordFish is designed to be a learning resource. You are encouraged to explore and edit the source code in `src/main.py` to add your own features or modify the behavior of the browser.

## ⚖️ License

This project is open for modification and educational use.
