
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
  <a href="#description">Description</a> •
  <a href="#hardware-components">Hardware Components</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#download">Download</a> •
  <a href="#credits">Credits</a> •
  <a href="#related">Related</a> •
</p>

![screenshot](https://github.com/Frapais/ESPHome_Oil_Level_Monitor/blob/main/IMG_20230109_153445.jpg)

## Description
### Hardware description
This sensor uses an ESP32 board that supports battery power/charging. The ESP32 also measures the battery voltage via an analog pin, through a voltage divider. The voltage divired is needed because the maximum voltage of the battery is **4.2V** while the ADC of the ESP32 can measure only up to **1.1V**. 
The oil level measurement is done with a waterproof ultrasonic sensor and its module pcb. However, you can probably use a regular ultrasonic sensor. 
The electronics were mounted inside a custom enclosure that was designed to screw on the lid of my oil tank.
### How the measurement works
This sensor works using an Ultrasonic sensor, to measure the level of a liquid in a tank.
In this particular case, the sensor is placed at the top of the tank, pointing down on the surface of the liquid.
This way, we can measure the distance of the liquid from the top of the tank, and, knowing the dimensions of the tank, we can calculate its volume.
Specifically, we measure the volume of the remaining liquid using the following formula:
$$remainingVolume=maxVolume - measuredVolume$$

where *maxVolume* is calculated from the dimensions of the tank (*Length, Width, Height*), and *measuredVolume* is calculated using the following formula:
$$measuredVolume = Length * Width * measuredDistance$$

Similarly, the consumed liquid can be calculated using the following formula:
$$consumedVolume = measuredVolume  - (maxVolume - initialVolume)$$
where *initialVolume* is the volume of the liquid when we start the consumption measurement

### General code flow
* ESP wakes up for **60 seconds**
  * Connects to Home Assistant
  * Samples **17 times** the oil surface distance and calculates an average
  * Samples the battery voltage and converts it to **percentage**
  * Calculates and updates the **consumed oil volume** and the **remaining oil volume**
* Falls to deep sleep for **29 minutes**

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

