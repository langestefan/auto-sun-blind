# Auto Sun Blind
Automatically control your sun blinds via home assistant based on the position of the sun.

## Custom Template

A jinja macro to track the position of a vertical cover based on the sun position to block out direct sunlight.

### How to import
Home Assistant 2023.4.0 or higher is required to use custom templates.

You can install it using HACS. HACS only supports custom templates in `experimental mode`. Click on the button to go directly to the right section.

Manual install is done by copying the contents of [`auto_sun_blind.jinja`](https://github.com/langestefan/auto-sun-blind/blob/main/auto_sun_blind.jinja) to a `.jinja` file in your `config/custom_templates` folder. Run the `homeassistant.reload_custom_templates` service call to load the file.

Click here for additional documentation and instructions on how to use it.

```yaml
{% from 'auto_sun_blind.jinja' import 'auto_sun_blind' %}
{{ auto_sun_blind() }}
```
## Blueprint
This project includes a blueprint that you can use without setting up a sensor.

Features:

    - Easy variable control with sliders
    - Time-out to save battery or reduce the amount of changing the cover position
    - Minimum percentage change to prevent the amount of changing the cover position by small percentage changes

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Flangestefan%2Fauto-sun-blind%2Fblob%2Fmain%2Fblueprints%2Fauto_sun_blind.yaml)

Click here for the full documentation for the Blueprint.