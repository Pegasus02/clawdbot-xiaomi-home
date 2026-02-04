# Clawdbot Xiaomi Home Skill 🏠 | 小米家居技能包

[English] | [中文](#中文说明)

---

## English

A specialized skill for **Clawdbot** that enables code-level control of Xiaomi (Mi Home) devices over the local network using the `python-miio` library.

### 🚀 Features
- **Local Network Control**: Fast, direct communication without relying on heavy cloud APIs.
- **Built-in Token Extractor**: Includes a script to easily fetch your device IPs and Tokens from Xiaomi Cloud.
- **Pre-configured Workflows**: Ready-to-use commands for smart plugs (e.g., water heaters), humidifiers, and rice cookers.
- **Automatic Dependency Fix**: Solves common library conflicts (like the `click` version issue) automatically.

### 📦 Installation

**Via ClawdHub (Recommended):**
```bash
clawdhub install xiaomi-home
```

**Via Git:**
```bash
git clone https://github.com/Pegasus02/clawdbot-xiaomi-home.git
```

### 🛠️ Quick Start
1. **Get Tokens**: Run the bundled script:
   ```bash
   python3 scripts/token_extractor.py
   ```
2. **Configure**: Add your device details to `references/devices.md`.
3. **Command**: Tell Clawdbot: *"Turn on the water heater"* or *"Check humidifier status"*.

---

## 中文说明

这是一个专为 **Clawdbot** 打造的米家设备控制技能包。它利用 `python-miio` 库，实现了在局域网内对小米智能家居设备的代码级直接控制。

### 🚀 核心特性
- **本地化控制**：直接在局域网内通信，响应极快，不完全依赖复杂的云端 API。
- **内置 Token 提取器**：自带提取脚本，轻松从小米账号同步所有设备的 IP 和 32 位 Token 密钥。
- **预设工作流**：支持智能插座（如热水器控制）、加湿器、米家小饭煲等多种常见设备。
- **自动环境优化**：安装时自动处理 Python 依赖冲突（如 `click` 版本问题），确保开箱即用。

### 📦 安装方式

**通过 ClawdHub (推荐):**
```bash
clawdhub install xiaomi-home
```

**通过 Git 手动安装:**
```bash
git clone https://github.com/Pegasus02/clawdbot-xiaomi-home.git
```

### 🛠️ 快速开始
1. **获取钥匙**：运行内置的提取脚本：
   ```bash
   python3 scripts/token_extractor.py
   ```
2. **配置列表**：将您的设备信息填入 `references/devices.md`。
3. **下达指令**：对着机器人喊：“打开热水器”或“查看加湿器状态”。

---

## 🔗 Links | 相关链接
- **ClawdHub**: [https://www.clawhub.ai/s/xiaomi-home](https://www.clawhub.ai/s/xiaomi-home)
- **GitHub**: [https://github.com/Pegasus02/clawdbot-xiaomi-home](https://github.com/Pegasus02/clawdbot-xiaomi-home)

Developed with 🦞 by **@Pegasus02**
