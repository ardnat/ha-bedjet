# Home Assistant BedJet

This project contains a climate entity that provides control of a [BedJet](https://bedjet.com) device.

## Installation (HACS) - Recommended

0. Have [HACS](https://custom-components.github.io/hacs/installation/manual/) installed, this will allow you to easily update
1. Add `https://github.com/asheliahut/ha-bedjet` as a [custom repository](https://custom-components.github.io/hacs/usage/settings/#add-custom-repositories) as Type: Integration
2. Click install under "HA-BedJet", restart your instance.

## Installation (Manual)

1. Download this repository as a ZIP (green button, top right) and unzip the archive
2. Copy `/custom_components/bedjet` to your `<config_dir>/custom_components/` directory
   - You will need to create the `custom_components` folder if it does not exist
   - On Hassio the final location will be `/config/custom_components/bedjet`
   - On Hassbian the final location will be `/home/homeassistant/.homeassistant/custom_components/bedjet`

## Configuration

Follow the configuration flow in devices & services

Configuration variables:

- **mac** (_Optional_): Bluetooth MAC address of your BedJet, if you want to specify. If not specified, this integration will search for all BedJets within range.

## Communication Protocol

This integration communicates with BedJet devices using **Bluetooth Low Energy (BLE)**, not traditional TCP/IP network ports. The integration uses BLE GATT characteristics for communication:

- **Command UUID**: `00002004-bed0-0080-aa55-4265644a6574` - Used to send commands to the BedJet
- **Subscription UUID**: `00002000-bed0-0080-aa55-4265644a6574` - Used to receive status updates from the BedJet

No network ports are used; all communication happens over Bluetooth within your local Bluetooth range (typically ~10-30 meters).

## Screenshot

![screenshot](https://i.imgur.com/Y836CWU.png)
