Home Assistant Custom Component to obtain exchange rates from https://currencylayer.com/

Obtain an API from https://currencylayer.com/signup?plan=1 (free plan allows 1000 requests per month)

Add the following in your configuration.yaml:

```yaml
sensor:
  platform: currencylayer
  api_key: your_api_key
  base: USD #optional
  quote: EUR
  name: USDEUR #optional
```

Currently, only 1 sensor can be added in the configuration. However, the attributes have the rates for all the other currencies, allowing you to add additional exchange rate sensors using value template. For example, to add another sensor for USDINR, just add the following to your configuration.yaml:
```
sensor:
  usdinr:        
  value_template: ' {{ states.sensor.usdeur.attributes.USDINR }}'    
```

## Installation

Place the file currencylayer.py in the /custom_components/sensor/ directory (you may need to create it) wherever your hass config file lies. Restart hass.
