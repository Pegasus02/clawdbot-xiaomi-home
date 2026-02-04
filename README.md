# Clawdbot Xiaomi Home Skill 🏠

This is a specialized skill for **Clawdbot** that enables code-level control of Xiaomi (Mi Home) devices over the local network.

## 🚀 Features
- **Local Control**: Direct protocol-level communication via `python-miio`.
- **Pre-configured Workflows**: Support for smart plugs (hot water heaters), humidifiers, and rice cookers.
- **Dependency Fix**: Automatically handles the common `click` library version conflict.

## 📦 Installation

You can install this skill directly via **ClawdHub**:

```bash
clawdhub install xiaomi-home
```

Or manually clone this repo into your `skills/` directory.

## 🛠️ Usage

### Setup
1. Ensure your device running Clawdbot is on the same LAN as your Xiaomi devices.
2. Obtain your device IP and Token using [Xiaomi Cloud Tokens Extractor](https://github.com/PiotrMachowski/Xiaomi-Cloud-Tokens-Extractor).
3. Add your devices to `references/devices.md`.

### Examples
- **Check Status**: `自嘲熊，查看热水器状态`
- **Toggle Power**: `大龙虾，打开加湿器`

## 🔗 Links
- **ClawdHub Page**: [https://www.clawhub.ai/s/xiaomi-home](https://www.clawhub.ai/s/xiaomi-home)
- **Clawdbot Official**: [https://clawd.bot](https://clawd.bot)

---
Developed by **@Pegasus02** 🦞
