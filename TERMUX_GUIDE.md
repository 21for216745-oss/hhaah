# Plasma Discord Self-Bot: Termux Installation Guide

This guide will help you run the Plasma Discord Self-Bot on your Android device using Termux.

## 1. Install Termux
Download and install Termux from [F-Droid](https://f-droid.org/en/packages/com.termux/) (do not use the Play Store version as it is outdated).

## 2. Update Packages
Open Termux and run:
```bash
pkg update && pkg upgrade
```

## 3. Install Dependencies
Run the following command to install Python and other required tools:
```bash
pkg install python git binutils
```

## 4. Clone the Repository
Clone your project (or copy the files to your device):
```bash
git clone <your-repo-url>
cd Plasma-Selfbot
```

## 5. Install Python Packages
Install the required libraries:
```bash
pip install -r requirements.txt
```

## 6. Run the Bot
Start the bot using:
```bash
python main.py
```

## Tips for Termux
- **Stay Awake**: Run `termux-wake-lock` to prevent Android from killing the bot when the screen is off.
- **Backgrounding**: You can use `tmux` or `screen` to keep the bot running in the background.
- **Copy/Paste**: Long press in the Termux terminal to access the copy/paste menu for your token.
