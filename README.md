# homebridge-sonoff-tasmota-http-switch

This is a plugin for [homebridge](https://github.com/nfarina/homebridge) which makes it possible to control modded Sonoff Basic devices with [Tasmota](https://github.com/arendst/Sonoff-Tasmota) firmware through HTTP only

Unlike generic homebridge-sonoff-tasmota-http, this Homebridge plugin publishes Sonoff as a Switch class device and gives an ability not only to switch between states, but to trigger the switch into ON state for 1-10 seconds like a button.

This project is a pre-stage for a HTTP-only plugin for a Garage Door Opener, presented in the article below.
Inspired by http://www.instructables.com/id/Sonoff-Garage-Door-Opener/, Step 2:
![alt text](https://cdn.instructables.com/FFU/9DM4/J80GJC0H/FFU9DM4J80GJC0H.LARGE.jpg)





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
