# homebridge-intesisbox

[Homebridge](https://github.com/nfarina/homebridge) plugin for [Intesisbox](https://www.intesisbox.com) devices including [ASCII](https://www.intesisbox.com/en/ascii/gateways/) and [WMP/Wi-Fi gateways](https://www.intesisbox.com/en/wifi/gateways/), integrating various reverse-cycle air conditioners by Daikin, Fujitsu, Mitsubishi, Panasonic, Toshiba, and others with [Apple HomeKit](https://developer.apple.com/homekit/) for control from iPhones and other Apple devices

I use an [Intesisbox FJ-RC-WMP-1](https://www.intesisbox.com/en/fujitsu-ascii-wifi-vrf-fj-rc-wmp-1/gateway/) connected to a Fujitsu ducted unit ([ARTG24LMLC](https://www.fujitsugeneral.com.au/product/artg24lmlc---7.1kw(c)-8.0kw(h))) and this works great.

# Installation

1. Install homebridge:
   ```
   npm install -g homebridge
   ```

2. Install this plugin:
   ```
   npm install -g homebridge-intesisbox
   ```

3. Update your configuration file. See configuration options below.

4. Restart homebridge.

# Configuration

Add an accessory to your homebridge `config.json`, like:

```json
{
  "accessories": [
    {
      "accessory": "Intesisbox",
      "name": "Air Conditioner",
      "host": "192.168.0.10"
    }
  ]
}
```

Fields:

- `accessory` must always be `Intesisbox`
- `name` defaults to `Intesisbox` but can be set to whatever your device to be called, like `Air Conditioner`
- `host` must be the IP address of your device
- `port` defaults to `3310` but can be overriden
- `number` defaults to `1` but can be set to your unit number if you have multiple units connected to the same device

# TODO

- Turn into a platform plugin
- Add device auto-discovery (`DISCOVER` command over UDP)

# References

- [Intesisbox WMP ASCII protocol specs](https://www.intesisbox.com/intesis/product/media/intesisbox_wmp_protocol_specs_en.pdf?v=2.2)

# Acknowledgements

This package was originally forked from [zylantha's first attempt](https://github.com/zylantha/homebridge-intesisbox) but then completely rewritten, with reference to [wailuen's homebridge-sensibo-sky plugin](https://github.com/wailuen/homebridge-sensibo-sky).
