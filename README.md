# Curtain card

[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)
[![buymeacoffee_badge](https://img.shields.io/badge/Donate-Buymeacoffee-orange?style=for-the-badge)](https://www.buymeacoffee.com/Deejayfool)

This card allows to open, close or set a curtain to the opening rate you want.

![curtain card](https://raw.githubusercontent.com/Deejayfool/hass-shutter-card/master/images/shutter-card.gif)

## Configuration

### General

| Name | Type | Required | Default | Description
| ---- | ---- | -------- | ------- | -----------
| type | string | True | - | Must be "custom:curtain-card"
| title | string | False | - | Title of the card

### Entities

| Name | Type | Required | Default | Description
| ---- | ---- | -------- | ------- | -----------
| entity | string | True | - | The curtain entity ID
| name | string | False | _Friendly name of the entity_ | Name to display for the curtain
| buttons_position | string | False | `left` | Set buttons on `left` or on `right` of the curtain
| title_position | string | False | `top` | Set title on `top` or on `bottom` of the curtain
| invert_percentage | boolean | False | `false` | Set it to `true` if your curtain is 100% when it is closed, and 0% when it is opened

_Remark : you can also just give the entity ID (without to specify `entity:`) if you don't need to specify the other configurations._

### Sample

```yaml
type: 'custom:curtain-card'
title: My curtain
entities:
  - entity: cover.left_living_curtain
    name: Left curtain
    buttons_position: left
    title_position: bottom
  - cover.bedroom_curtain
```

## Install

If you use HACS, the resources will automatically be configured with the needed file.

If you don't use HACS, you can download js file from [latest releases](https://github.com/salmahassan7979/Curtain-Card-hass.git). Drop it then in `www` folder in your `config` directory. Next add the following entry in lovelace configuration:

```yaml
resources:
  - url: /local/curtain-card.js
    type: module
```
