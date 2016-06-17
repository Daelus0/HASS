Home Assistant Custom Component to obtain exchange rates from https://openexchangerates.org/

Obtain an API from https://openexchangerates.org/signup/free (free plan allows 1000 requests per month)

Enable in config as such:

```yaml
sensor:
  platform: openexchangerates
  api_key: your_api_key
  base: USD #optional
  quote: EUR
  name: USDEUR #optional
```

Currently, only 1 sensor can be added in the configuration. However, the attributes have the rates for all the other currencies, allowing you to add additional exchange rate sensors using value template such as:
```
sensor:
  usdinr:        
  value_template: ' {{ states.sensor.usdeur.attributes.INR }}'    
```

## Installation

Place the file openexchangerates.py in the /custom_components/sensor/ directory (you may need to create it) wherever your hass config file lies. Restart hass.
