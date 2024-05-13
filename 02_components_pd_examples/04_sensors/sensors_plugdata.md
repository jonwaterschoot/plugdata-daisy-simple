---
layout: default
title: Sensors
nav_order: 13
parent: Components Plugdata examples
---

# Sensors

Various sensors can be connected and are supported. There's a list you can consult with a description of the available parameters at pd2dsy

This page will use the MPR121 touch sensor as an example.

{: .attention}
>**This Page isn't ready yet**
>
>On [the page about setting up the custom json file](01_install_setup_plugdata\03_custom_json_board\03_custom_json_board.html) an example for the touchsensor mpr121 is shown.
>
> - Some extra steps explained there are needed (altering the 'mother' file component_defs.json that is included in the Toolchain)
>
> - Time based effects like delay or reverb seem to be very unstable/ non functioning with the mpr121 

Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources


  ***

Extra list / draft page to implement or link:

In the future I'll be testing a simple lightsensor, the motion sensor (BNO055), and distance measuring sensor (VL53L1X)

# pd2dsy supported Sensors

List of supported / implemented sensors in pd2dsy:

[GitHub - electro-smith/pd2dsy: Utility for converting Pure Data (Vanilla) patches to Daisy projects.](https://github.com/electro-smith/pd2dsy?tab=readme-ov-file#interacting-with-the-daisy-io)

Full list in the components_defs.json file:

[](https://github.com/electro-smith/json2daisy/blob/main/src/json2daisy/resources/component_defs.json)

connecting these sensors to the daisy and adding them in the custom json should be supported.

Note that for e.g. the touchsensor mpr121 there’s a bug where the pins are not getting assigned as intended.

[GitHub - electro-smith/pd2dsy: Utility for converting Pure Data (Vanilla) patches to Daisy projects.](https://github.com/electro-smith/pd2dsy?tab=readme-ov-file#interacting-with-the-daisy-io)

## BME280 - Humidity sensor

measuring relative humidity, barometric pressure and ambient temperature

### Price range:

1 EUR (Aliexpress)- 15 EUR  (Adafruit stemma breakout)

### Connection / Pins:

 I²C and SPI

[Adafruit BME280 I2C or SPI Temperature Humidity Pressure Sensor](https://www.adafruit.com/product/2652)

[Humidity Sensor BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/)

Humidity sensor measuring relative humidity, barometric pressure and ambient temperature

| BME280 | --- | Returns the temperature in degrees C. |
| --- | --- | --- |
| BME280 | _temp | Behaves the same as the default option. |
| BME280 | _hum | Returns the humidity in relative percentage. |
| BME280 | _press | Returns the pressure in pascals (1 atm ~= 100 kPa) |
| BME280 | _alt | Returns the estimated altitude in meters |

## BMP390 - barometric pressure - temperature

The BMP390 is a very small, low-power and low-noise 24-bit absolute barometric pressure sensor. The digital, high-performance sensor is ideally suited for a wide range of altitude tracking applications.

[Pressure Sensor BMP390](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp390/)

[Adafruit BMP390 - Precision Barometric Pressure and Altimeter](https://www.adafruit.com/product/4816)

### Price range

1 EUR Ali Express

12 EUR Adafruit, Stemma breakout

### Pinout / Connection:

| BMP390 | --- | Returns the temperature in degrees C. |
| --- | --- | --- |
| BMP390 | _temp | Behaves the same as the default option. |
| BMP390 | _press | Returns the pressure in pascals (1 atm ~= 100 kPa) |
| BMP390 | _alt | Returns the estimated altitude in meters |

| Type | _variant | Behavior |
| --- | --- | --- |
| Inputs | --- | --- |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
| BMP390 | --- | Returns the temperature in degrees C. |
| BMP390 | _temp | Behaves the same as the default option. |
| BMP390 | _press | Returns the pressure in pascals (1 atm ~= 100 kPa) |
| BMP390 | _alt | Returns the estimated altitude in meters |
| Hall Sensor | --- | Returns the current state of the sensor (0 if no field present, otherwise 1). |
| Hall Sensor | _count | Returns the number of times the hall sensor has been activated. |
| TLV93D | --- | Returns the magnitude of the field's force vector in uT (i.e. the amount of field). |
| TLV93D | _x, _y, _z | Returns the field's strength in the given axis in uT. |
| TLV93D | _amount | Behaves the same as the default option. |
| TLV93D | _azimuth | Returns the field's azimuth for spherical coordinates. |
| TLV93D | _polar | Returns the field's 3D inclination for spherical coordinates. |
| MPR121 | --- | Returns whether channel 0 is touched according to the threshold. |
| MPR121 | _ch0 ... _ch11 | Returns a 1 if the given channel is touched according to the threshold, otherwise 0. |
| MPR121 | _ch0_raw ... _ch11_raw | Returns the raw sensor data for the given channel as a 10-bit unsigned integer. |
| APDS9960 | --- | Returns the current read gesture (1-4) if detected, otherwise 0. |
| APDS9960 | _gest | Behaves the same as the default option. |
| APDS9960 | _prox | Returns the detected proximity in undefined units (meant for relative distance detection). |
| APDS9960 | _red, _green, _blue, _clear | Returns the detected brightness of the given color as a 16-bit unsigned integer. |
| VL53L1X | --- | Returns the distance measurement in mm. |
| Neo Trellis | --- | Sends a bang when the first button (index 0) is pressed. |
| Neo Trellis | _0 ... _15 | Sends a bang when the given button is pressed. |
| Neo Trellis | _0_falling ... _15_falling | Sends a bang when the given button is released. |
| Neo Trellis | _0_state ... _15_state | Returns the current state of the given button (1 = pressed, 0 = released). |
| BNO055 | --- | Returns the X component of the accelerometer in m/s^2. |
| BNO055 | _accel_x, _accel_y, _accel_z | Returns the given axis from the accelerometer in m/s^2. |
| BNO055 | _magnet_x, _magnet_y, _magnet_z | Returns the given axis from the magnetometer in uT. |
| BNO055 | _gyro_x, _gyro_y, _gyro_z | Returns the given axis from the gyroscope in dps (degrees per second). |
| BNO055 | _euler_x, _euler_y, _euler_z | Returns the rotation along the given axis in degrees. |
| BNO055 | _linear_accel_x, _linear_accel_y, _linear_accel_z | Returns the linear acceleration in the given axis in m/s^2. |
| BNO055 | _grav_x, _grav_y, _grav_z | Returns the acceleration due to gravity along the given axis in m/s^2. |
| BNO055 | _quat_w, _quat_x, _quat_y, _quat_z | Returns the orientation represented as a quaternion. |
| Outputs | --- |  |
| Stepper Motor | --- | Expects a floating point value of any arbitrary size, representing the number of steps to rotate. The sign of the number determines direction. |
| Stepper Motor | _release | Triggers the stepper motor to relax its fields when a positive value is received, allowing the motor to spin freely. |
| DC Motor | --- | Expects a floating point value from -1 to 1. The magnitude controls the speed, the sign controls direction, and a value of zero stops the motor. |
| Neo Trellis LEDs | _0 ... _15 | Expects an integer from 0-255 to control the led brightness of the corresponding pad. |