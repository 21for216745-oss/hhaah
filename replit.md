# Plasma Discord Self-Bot

## Overview

Plasma is a Discord self-bot built with Python using the `discord.py-self` library. Self-bots operate using a user's personal Discord token rather than a bot token, allowing automation of user account actions. The bot provides various utility features including auto-reply functionality, AFK mode, copycat mode, and text-to-speech capabilities.

**Important Note:** Self-bots violate Discord's Terms of Service and can result in account termination. This project is for educational purposes.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Core Framework
- **Discord Library**: Uses `discord.py-self`, a fork of discord.py designed for self-bot functionality
- **Command System**: Built on `discord.ext.commands` with a configurable command prefix (default: `.`)
- **Configuration**: JSON-based configuration stored in `config/config.json`

### Key Components

| Component | Purpose |
|-----------|---------|
| Token Authentication | User enters Discord token at runtime via console input |
| Auto-Reply System | Cycles through configured messages for specific channels/users |
| AFK Mode | Automatic responses when user is away |
| Copycat Mode | Mirrors messages from specified users |
| Text-to-Speech | Uses gTTS (Google Text-to-Speech) for audio generation |

### Configuration Management
- Configuration is loaded from `config/config.json` at startup
- `save_config()` function persists configuration changes
- Supports dynamic updates to remote-users, auto-reply settings, AFK status, and copycat targets

### Design Patterns
- **Iterator Pattern**: Uses `itertools.cycle` for rotating auto-reply messages
- **Single Entry Point**: All functionality runs through `main.py`

## External Dependencies

### Python Packages
| Package | Purpose |
|---------|---------|
| `discord.py-self` | Discord self-bot API wrapper |
| `requests` | HTTP requests for external APIs |
| `colorama` | Terminal color formatting |
| `gtts` | Google Text-to-Speech integration |
| `qrcode` | QR code generation |
| `pyfiglet` | ASCII art text generation |

### External Services
- **Discord API**: Primary service for bot functionality (accessed via user token)
- **Google TTS API**: Text-to-speech conversion (via gTTS library)

### File Structure
```
├── main.py              # Entry point and core bot logic
├── requirements.txt     # Python dependencies
└── config/
    └── config.json      # Bot configuration (prefix, auto-reply, AFK, copycat)
```

### Security Considerations
- Discord token is entered at runtime, not stored in files
- Token should never be committed to version control
- The bot runs with full user account permissions