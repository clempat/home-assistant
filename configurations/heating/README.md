# Heating

We have Infrared heating from [RedTherm](https://www.redtherm.de/). We control them with a DIY raspberry pi with relay Board connected to Hager ERC218.

# Hardware

- Raspberry PI
- Relay Board 16
- [ERC218 Hager](https://www.eibmarkt.com/cgi-bin/eibmarkt.storefront/6260726c014cb4c0274aac1e0402061c/Product/View/NS5705880)
- Xiaomi Aqara Temperature and Humidity Sensors

# Integration

- MQTT
- Phoscon Deconz
- Generic Thermostats
- Template Sensors (To get the temperature per room, as soon a new sensors is added to the room, it will count into the average)

# Features

- [x] Control individually Heaters
- [x] Schedule comfort/Eco consign
- [x] [Stop heaters when windows open](../../blueprints/automation/clempat/windows_heating.yaml)
- [x] Temperature per room
- [ ] Global control with Holiday/Summer/Winter...
- [ ] History of consumption and mail with statistics
- [ ] Alert when windows is open and it is cold outside
- [ ] Alert when default on sensors or heaters

# Notes

We use [MQTT-IO](mqtt-io.app/) but I am having some issue when the broker goes offline and back online. The heaters stay offline.
