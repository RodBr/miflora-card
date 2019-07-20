# MiFlora Card

A Home Assistant Lovelace card to report MiFlora sensors

![miflora-card](miflora-card.jpg)


## Options

| Name             | Type    | Default      | Description                                   |
| ---------------- | ------- | ------------ | --------------------------------------------- |
| type             | string  | **Required** | `custom:miflora-card`                         |
| title            | string  | **Required** | Name of the plant being monitored             |
| image            | string  | **Required** | Path to an image of the plant being monitored |
| min_moisture     | integer | Optional     | Minimum moisture content for this plant       |
| max_moisture     | integer | Optional     | Maximum moisture content for this plant       |
| min_conductivity | integer | Optional     | Minimum conductivity reading for this plant   |
| min_temperature  | integer | Optional     | Minimum temperature for this plant            |
| entities         | list    | **Required** | A list sensors to be monitored                |


## Installation

1. Install the `miflora-card` component by copying `miflora-card.js` to `<config directory>/www/miflora-card.js`


2. Link `miflora-card` inside your `ui-lovelace.yaml`

```yaml
resources:
  - url: /local/miflora-card.js
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
  - moisture:sensor.miflora_1_moisture
  - intensity:sensor.miflora_1_light_intensity
  - temperature:sensor.miflora_1_temperature
  - conductivity:sensor.miflora_1_conductivity
  - battery:sensor.miflora_1_battery

```
