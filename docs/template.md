# Custom Template

A jinja macro to track the position of a vertical cover based on the sun position to block out direct sunlight.

### How to import
Home Assistant 2023.4.0 or higher is required to use custom templates.

You can install it using HACS. HACS only supports custom templates in `experimental mode`. Click on the button to go directly to the right section.

Manual install is done by copying the contents of [`auto_sun_blind.jinja`](https://github.com/langestefan/auto-sun-blind/blob/main/auto_sun_blind.jinja) to a `.jinja` file in your `config/custom_templates` folder. Run the `homeassistant.reload_custom_templates` service call to load the file.

```yaml
{% from 'auto_sun_blind.jinja' import 'auto_sun_blind' %}
{{ auto_sun_blind() }}
```

## Variables

|name|default|unit|range|description|
|---|---|---|---|---|
|`azimuth`| 136 | degrees| [0, 359] | The angle of the window measured from the North. |
|`distance`| 0.5 |M| [0,] |The distance from the window you want the beginning of the shadow to fall.|
|`height`| 1.96 |M| [0,]|The height of your window in meters (or actually the maximum height of your blinds, but for most people this will be the same number ofcourse)|
|`min_height`| 0 |M| [0,] |The minimum height in meters when the blinds are fully open. This will be 0 in most cases.|
|`def_height`| 60|%| [0, 100] | The position for the cover to return to when the sun is not within the specified range|
|`fov_left`| 90 |degrees |[0, 90] |The angle on the left side of the window that falls within the range.| 
|`fov_right`| 90 |degrees| [0, 90] |The angle on the right side of the window that falls within the range.| 
|`elev_min`| 0 |degrees| [0, 90] | The minimal elevation angle | 
|`elev_max`| 90 |degrees| [0, 90] |The maximum elevation angle|