# Maico KWL Modbus Integration for Home Assistant

This repository provides a ready-to-use configuration for integrating Maico KWL ventilation units into Home Assistant via Modbus.

## Installation

1. **Download the configuration file**  
   Copy [`maico.yml`](maico.yml) to your Home Assistant configuration directory.

2. **Update the IP address**  
   Edit `maico.yml` and replace the placeholder IP with the IP address of your Maico KWL device.

3. **Modify `configuration.yaml`**  
   Add the following lines to your `configuration.yaml` to include the Maico configuration:

   ```yaml
   homeassistant:
     packages:
       maico: !include maico.yml
4. **Restart Home Assistant**
   Restart Home Assistant to apply the changes.
