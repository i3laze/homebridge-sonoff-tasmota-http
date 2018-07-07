# homebridge-sonoff-tasmota-http-switch

This is a plugin for [Homebridge](https://github.com/nfarina/homebridge) which makes it possible to control *modded* Sonoff Basic devices with [Tasmota](https://github.com/arendst/Sonoff-Tasmota) firmware through HTTP only.

Unlike generic [homebridge-sonoff-tasmota-http](https://github.com/ageorgios/homebridge-sonoff-tasmota-http), this plugin publishes Sonoff as a Switch class device and gives an ability not only to switch between states (which a parent plugin could easily do), but to trigger ON state (close the cirtcuit) for 0,1-10 seconds like a button.

This project is a pre-stage for a HTTP-only plugin for a Sonoff-based Garage Door Opener, presented in this article:
http://www.instructables.com/id/Sonoff-Garage-Door-Opener/

Below is an *optional* hardware modification (more details in [Step 2](http://www.instructables.com/id/Sonoff-Garage-Door-Opener/)) that transforms Sonoff's output pins into an isolated circuit, able to toggle any electric circuits (running any voltage!), which have control pins, like garage-door control unit:
![alt text](https://cdn.instructables.com/FC1/2N7E/J80GJBW5/FC12N7EJ80GJBW5.LARGE.jpg) 
*Max.voltage is limited by Sonoff's relay SRD-05VDC-SL-C to 30V DC / 250V AC, max current is 20A.*

The Tasmota compatible version of the plugin is 5.11.0 and later

If you need compatibility with previous Tasmota versions, fork this commit: https://github.com/ageorgios/homebridge-sonoff-tasmota-http/tree/6f73a32fd8ae01f16813f8f0bd3844d3da469e4d

# Information
```
http://sonoff/cm?cmnd=Power
http://sonoff/cm?cmnd=Power%20On
http://sonoff/cm?cmnd=Power%20Off
```

## Example config

```json
{
  "accessory": "SonoffTasmotaHTTP",
  "name": "Sonoff",
  "hostname": "The hostname of the Sonoff device"
}
```

## Multiple Relays

```json
{
  "accessory": "SonoffTasmotaHTTP",
  "name": "Sonoff",
  "relay": "2",
  "hostname": "The hostname of the Sonoff device"
}
```

## Password specified in Web Interface

```json
{
  "accessory": "SonoffTasmotaHTTP",
  "name": "Sonoff",
  "password": "The password from the web interface",
  "hostname": "The hostname of the Sonoff device"
}
```
