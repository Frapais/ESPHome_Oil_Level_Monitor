
<h1 align="center">
  <br>
  ESPHome Oil Level Sensor
  <br>
</h1>

<h4 align="center">A custom <a href="https://github.com/esphome/esphome" target="_blank">ESPHome</a> sensor for <a href="https://github.com/home-assistant" target="_blank">Home Assistant</a>.</h4>

<p align="center">
  <a href="https://saythanks.io/to/Frapais">
      <img src="https://img.shields.io/badge/SayThanks.io-%E2%98%BC-1EAEDB.svg">
  </a>
  <a href="https://paypal.me/kostasparaskevas?country.x=GR&locale.x=en_US">
    <img src="https://img.shields.io/badge/$-donate-ff69b4.svg?maxAge=2592000&amp;style=flat">
  </a>
</p>

<p align="center">
  <a href="#hardware-components">Hardware Components</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#download">Download</a> •
  <a href="#credits">Credits</a> •
  <a href="#related">Related</a> •
  <a href="#license">License</a>
</p>

![screenshot](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/IMG_20230109_153445.jpg)

## Hardware Components

* [ESP32](https://www.amazon.com/Adafruit-PID-3591-HUZZAH32-pre-soldered/dp/B079QGXX88/ref=sr_1_3?keywords=esp32+battery&qid=1673281668&sprefix=esp32+bat%2Caps%2C237&sr=8-3) board with battery charging capability
* Li-Ion battery
* [Waterproof](https://www.amazon.com/Waterproof-Ultrasonic-JSN-SR04T-Integrated-Transducer/dp/B07FQCNXPP) Ultrasonic sensor
* 2 resistors for measuring the battery voltage

## How To Use

You need to have a [Home Assistant](https://github.com/home-assistant) server with [ESPHome](https://github.com/esphome/esphome) plugin working.
If so, follow these steps:

* Connect the hardware components according to the [schematic](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/Rough%20schematic.png)
* Download the YAML code for this sensor and make the required changes in the parameters according to your use-case
* Create a new sensor in your ESPHome dashboard
* Copy your customized YAML code to the sensor's YAML code
* Download and 3D print the [electronics enclosure](https://www.thingiverse.com/thing:5776524), or design your own according to your needs.


<!-- > **Note**
> If you're using Linux Bash for Windows, [see this guide](https://www.howtogeek.com/261575/how-to-run-graphical-linux-desktop-applications-from-windows-10s-bash-shell/) or use `node` from the command prompt. -->


## Download

* [YAML](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/fuel-level-sensor.yaml) code
* [3D files](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/Oil%20level%20sensor%20enclosure.stl)
* [schematic](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/Rough%20schematic.png)

## Credits

This software uses the following platforms:

- [Home Assistant](https://www.home-assistant.io/)
- [ESPHome](https://esphome.io/)

## Related

You can find similar code in the official Ultrasonic sensor implementation page of ESPHome
[Ultrasonic sensor](https://esphome.io/components/sensor/ultrasonic.html)

## Support

<a href="https://www.buymeacoffee.com/frapais" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/purple_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>





> GitHub [@frapais](https://github.com/Frapais) &nbsp;&middot;&nbsp;
> Instagram [@worked_first_time](https://www.instagram.com/worked_first_time/)

