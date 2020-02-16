# Projects

## Smart doorbell

- ESP32 Board with:
  - Camera module
  - Buttons
  - PIR-sensor
  - Display (not needed but it was bundled with the board)
- Relay-board
- Doorbell Chime

| |
|----|
| ![Doorbell Chime](images/doorbell_chime.jpg) |
| ![ttgocam](images/ttgocam_fisheye_lense.jpg) |

### Config-files
TODO

## Bluetooth tracking hub
- ESP32 Board with:
  - Bluetooth
  - WiFi

### Track presence

### Tracking devices

### Tracking sensors

#### Plantsensor
| |
|----|
| ![Xiaomi MiFlora](images/Xiaomi_MiFlora.jpg) |

#### Temperature and Humidity
| |
|----|
| ![Xiaomi MiJia](images/Xiaomi_MiJia.jpg) |

## Remotely controlled powerplugs

- Sonoff s20

| |
|--|
| ![Sonoff S20](images/sonoff_s20.jpg) |

### Software
[Sonoff HomeAssistant integration](https://github.com/AlexxIT/SonoffLAN/)

### Config-files
#### In config.yaml
```
# Enable sonoff integration
sonoff:
  username: !secret sonoff_user
  password: !secret sonoff_pass
#  reload: always  # update device list every time HA starts
```
#### In ui-lovelace.yaml

```
resources:
# Name: auto-entities-card
# Description: Automatically displays entities based on filters, makes ot easy to show several entities with minimal config effort
# Used in config? Yes
# Maintainer: HACS
# source: https://github.com/thomasloven/lovelace-auto-entities/blob/master/README.md
  - url: /community_plugin/lovelace-auto-entities/auto-entities.js
    type: module

# Name: fold-entity-row
# Description: Enables collapsible/expandable cards.
# Used in config? Yes
# Maintainer: HACS
  - url: /community_plugin/lovelace-fold-entity-row/fold-entity-row.js
    type: module

title: Home
views:

  - icon: mdi:toggle-switch
    title: Switches
    id: switches
    cards:

      - type: custom:auto-entities
        filter:
          include:
            - domain: switch
              entity_id: "switch.sonoff_*"
        card:
          type: custom:fold-entity-row
          head:
            type: section
            label: All Sonoff switches
```


## LED PSU Calculation
- Estiame 50 LED per 1 amp
- Add 1-2 amps for the controller

## LED
Parts:
- 2x [NodeMCU](http://s.click.aliexpress.com/e/pI2wgExm) - 
- 6x [Aluminum Channel (50cm)](http://s.click.aliexpress.com/e/sHXT8lzI) - 13m total
- 1x [5m 74px IP30, Black PCB](http://s.click.aliexpress.com/e/Kceu4gks) - 

### Kitchen cabinet lights
| |
|--|
| ![Aluminum Channel (50cm)](images/Aluminum_Channel_50cm_part1.jpg) |
| ![Aluminum Channel (50cm)](images/Aluminum_Channel_50cm_part2.jpg) |

## LCD info-screens
Parts:
- 2x [0.96 inch oled IIC Serial Yellow-blue OLED Display Module 128X64](https://www.aliexpress.com/item/32896971385.html) - 
- 1x [ESP32 WROOM-32, 240MHz](https://m.aliexpress.com/item/32864722159.html) - 

| |
|--|
| ![Yellow-blue OLED Display](images/oled_yellow_blue.jpg) |

### Description
- One screen to show the time and temperatures inside+outside.
- One screen to show delays and when the next train is scheduled for the subway. Useful when commuting to work.
