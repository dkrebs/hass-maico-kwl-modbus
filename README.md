# Maico KWL Modbus Integration for Home Assistant

Ready-to-use package for Maico KWL ventilation units via Modbus TCP (port 502).

## Installation

### Option A — Git submodule (recommended)

From your Home Assistant `/config` directory:

```bash
git submodule add https://github.com/dkrebs/hass-maico-kwl-modbus.git hass-maico-kwl-modbus
```

Create `packages/maico.yaml`:

```yaml
!include ../hass-maico-kwl-modbus/maico.yml
```

Add to `secrets.yaml`:

```yaml
maico_host: "192.168.178.157"  # IP of your Maico KWL
```

Ensure `configuration.yaml` loads packages:

```yaml
homeassistant:
  packages: !include_dir_named packages
```

Restart Home Assistant.

**Updates:** `git -C hass-maico-kwl-modbus pull` then restart HA (or reload Modbus).

### Option B — Copy file

1. Copy `maico.yml` to `config/packages/maico.yaml` (rename optional).
2. Set `host` to your device IP, or use `host: !secret maico_host` and add the secret.
3. Restart Home Assistant.

## Contents

- Modbus sensors, switches, and binary sensors for Maico KWL registers
- `input_select` helpers for writable settings
- Automations to sync helpers ↔ Modbus (modern `triggers` / `actions` syntax)
- Read-only sync of `sensor.maico_aktuelle_luftungsstufe` → `input_select.aktuelle_lueftungsstufe`

## Requirements

- Home Assistant Modbus integration
- Maico KWL reachable on the network (Modbus TCP, typically port 502)
