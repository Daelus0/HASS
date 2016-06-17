# Home Assistant Custom Component for WUnderground PWS

Based on initial work by [@kellbot](https://github.com/kellbot/hass-wunderground).

Requires an wunderground API key from http://api.wunderground.com/weather/api

Enable in config as such:

```yaml
sensor:
  platform: wunderground
  api_key: xxxxxxxxxx
  pws_id: XXXXXXXX # You can pick a PWS that is closest to your area
```
Refreshes every 5 minutes

## Installation

Place the file wunderground.py in /custom_components/sensor/ directory (you may need to create it) wherever your hass config file lies. Restart hass.
