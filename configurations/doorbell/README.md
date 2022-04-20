# Doorbell

It is not a smart doorbell as the gate is shared with an other house. We are using an DIY esphome + Some electronics to listen when contact close (Someone push the doorbell). We use SNCF jingle when someone ring the bell.

# Hardware

- nodemcuv2
- Some Electronics
- [Camera](../camera/README.md)
- [Notify](../notify/README.md)

# Integrations

- ESPHome

# Features

- [x] Run SNCF Jingle when someone ring the bell
- [x] Send IOS notification with camera feed
- [ ] Show camera feed on Google Nest Home
- [ ] Silent first floor when kids sleeping

# Notes

Code:

```yaml
captive_portal:
switch:
  - platform: gpio
    id: relay
    name: "Gate Open Switch"
    pin: D3
    restore_mode: ALWAYS_OFF
    icon: "mdi:gate"
    inverted: true
    on_turn_on:
      - delay: 3s
      - switch.turn_off: relay

binary_sensor:
  - platform: gpio
    name: Doorbell
    pin:
      number: D2
      mode:
        input: true
    filters:
      - delayed_on: 200ms
```
