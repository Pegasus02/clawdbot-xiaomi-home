---
name: xiaomi-home
description: Control Xiaomi Home devices via local LAN using miiocli. Supports status checks, toggling power, and MIOT property manipulation for devices like smart plugs, humidifiers, and rice cookers.
metadata: {"clawdbot":{"emoji":"🏠","requires":{"bins":["miiocli"]},"install":[{"id":"pipx-miio","kind":"exec","command":"pipx install python-miio && /Users/$(whoami)/.local/pipx/venvs/python-miio/bin/python -m pip install 'click<8.1.0'","label":"Install python-miio via pipx (with click fix)"}]}}
---

# Xiaomi Home Control

This skill enables Clawdbot to control Xiaomi (Mi Home) devices over the local network using the `python-miio` library.

## Prerequisites

1. **Network**: The device running Clawdbot must be on the same local network as your Xiaomi devices.
2. **Credentials**: You need the **IP Address** and the **32-character Token** for each device.

### How to get Tokens
Use the bundled **Token Extractor** script:
1. Navigate to the skill folder.
2. Run: `python3 scripts/token_extractor.py`.
3. Log in with your Mi Home account.
4. Copy the IP and Token for your devices.

Alternatively, use the [original repo](https://github.com/PiotrMachowski/Xiaomi-Cloud-Tokens-Extractor).

## Configuration

Store your device information in a reference file (e.g., `references/devices.md`) in the following format:

```markdown
| Device | IP | Token | Model |
| :--- | :--- | :--- | :--- |
| Hot Water Heater | 192.168.1.50 | your_32_char_token | cuco.plug.v3 |
```

## Usage Examples

### Generic MIOT Device (e.g., Smart Plug)
Replace `<IP>` and `<TOKEN>` with your device details.

- **Check Status (Power)**:
  ```bash
  miiocli miotdevice --ip <IP> --token <TOKEN> get_property_by 2 1
  ```
- **Turn ON**:
  ```bash
  miiocli miotdevice --ip <IP> --token <TOKEN> raw_command set_properties '[{"siid": 2, "piid": 1, "value": true}]'
  ```
- **Turn OFF**:
  ```bash
  miiocli miotdevice --ip <IP> --token <TOKEN> raw_command set_properties '[{"siid": 2, "piid": 1, "value": false}]'
  ```

### Humidifier
- **Status**:
  ```bash
  miiocli airhumidifiermiot --ip <IP> --token <TOKEN> status
  ```

### Rice Cooker
- **Status**:
  ```bash
  miiocli cooker --ip <IP> --token <TOKEN> status
  ```

## Troubleshooting

- **Connection Timeout**: Ensure the device is powered on and reachable via `ping`.
- **Click Error**: If you see `TypeError: argument of type 'bool' is not iterable`, ensure `click<8.1.0` is installed in the miio virtual environment.
