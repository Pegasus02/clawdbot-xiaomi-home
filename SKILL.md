---
name: xiaomi-home
description: Control Xiaomi Home devices via local LAN using miiocli. Supports status checks, toggling power, and MIOT property manipulation for devices like smart plugs, humidifiers, and rice cookers.
metadata: {"clawdbot":{"emoji":"🏠","requires":{"bins":["miiocli"]},"install":[{"id":"pipx-miio","kind":"exec","command":"pipx install python-miio && /Users/$(whoami)/.local/pipx/venvs/python-miio/bin/python -m pip install 'click<8.1.0'","label":"Install python-miio via pipx (with click fix)"}]}}
---

# Xiaomi Home Control 🏠

Enable code-level control of Xiaomi (Mi Home) devices over the local network.

## 🛠️ Setup & Device Inventory

1. **Tokens**: Obtain device IPs and Tokens using the bundled script:
   ```bash
   python3 scripts/token_extractor.py
   ```
2. **Registry**: Store your device details in `references/devices.md` or `references/my_private_devices.md`.

## 🤖 Natural Language Intents

When the user gives a command, map it to the corresponding `miiocli` operation:

| User Intent | Device Type | Action | Technical Command (Example) |
| :--- | :--- | :--- | :--- |
| "打开热水器" | Smart Plug | Power ON | `miiocli miotdevice --ip <IP> --token <TOKEN> raw_command set_properties '[{"siid": 2, "piid": 1, "value": true}]'` |
| "关闭热水器" | Smart Plug | Power OFF | `miiocli miotdevice --ip <IP> --token <TOKEN> raw_command set_properties '[{"siid": 2, "piid": 1, "value": false}]'` |
| "加湿器开到最大" | Humidifier | Set Mode | `miiocli miotdevice --ip <IP> --token <TOKEN> set_property_by 2 5 3` |
| "煮饭了吗" | Rice Cooker | Check Status | `miiocli cooker --ip <IP> --token <TOKEN> status` |
| "查看所有状态" | All | Batch Check | Run `get_property_by 2 1` for all devices in `devices.md` |

## 💡 Usage Examples

### Generic MIOT Control (Modern Devices)
- **Check Property**: `miiocli miotdevice --ip <IP> --token <TOKEN> get_property_by <siid> <piid>`
- **Set Property**: `miiocli miotdevice --ip <IP> --token <TOKEN> set_property_by <siid> <piid> <value>`

### Specific Device Commands
- **Humidifier**: `miiocli airhumidifiermiot --ip <IP> --token <TOKEN> status`
- **Rice Cooker**: `miiocli cooker --ip <IP> --token <TOKEN> status`

## ⚠️ Troubleshooting
- **Timeout**: Ensure the Mac is on the same subnet (e.g., `192.168.28.x`).
- **Dependency Issue**: If you see `TypeError: argument of type 'bool' is not iterable`, verify `click<8.1.0` is installed.
