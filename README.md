[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)


# MiFlora Card

A Home Assistant Lovelace card to report MiFlora sensors

![miflora-card](https://github.com/lbouriez/lovelace-miflora-card/raw/master/miflora-card.png)

## Options

| Name             | Type    | Requirement  | Description                                   |
| ---------------- | ------- | ------------ | --------------------------------------------- |
| type             | string  | **Required** | `custom:miflora-card`                         |
| title            | string  | **Required** | Name of the plant being monitored             |
| image            | string  | **Required** | Path to an image of the plant being monitored |
| min_moisture     | integer | Optional     | Minimum moisture content for this plant       |
| max_moisture     | integer | Optional     | Maximum moisture content for this plant       |
| min_conductivity | integer | Optional     | Minimum conductivity reading for this plant   |
| min_temperature  | integer | Optional     | Minimum temperature for this plant            |
| entities         | list    | **Required** | A list sensors to be monitored                |

### Entities

| Name             | Type    | Requirement  | Description                                   |
| ---------------- | ------- | ------------ | --------------------------------------------- |
| entity           | string  | **Required** | Entity ID                                     |
| type             | string  | **Required** | Type of entity                                |
| name             | string  | Optional     | Custom name if you want to change it          |


## Installation

Use [HACS](https://hacs.xyz) or follow this [guide](https://github.com/thomasloven/hass-config/wiki/Lovelace-Plugins)


```yaml
resources:
  - url: /hacsfiles/lovelace-miflora-card/miflora-card.js
    type: js
```

3. Add a custom card in your `ui-lovelace.yaml`

```yaml
- type: custom:miflora-card
  title: 'Calathea Zebrina'
  image: images/calathea-zebrina.jpg
  min_moisture: 15
  max_moisture: 60
  min_conductivity: 350
  min_temperature: 12
  entities:
  - entity: sensor.miflora_1_moisture
    type: moisture
  - entity: sensor.miflora_1_light_intensity
    type: intensity
  - entity: sensor.miflora_1_temperature
    type: temperature
  - entity: sensor.miflora_1_conductivity
    type: conductivity
    name: Fertility
  - entity: sensor.miflora_1_battery
    type: battery
```
