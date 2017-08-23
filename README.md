---
services: iot-hub
platforms: arduino
author: xshi
---

# IoT Hub SparkFun ESP8266 Thing-Dev Client application
[![Build Status](https://travis-ci.org/Azure-Samples/iot-hub-SparkFun-ThingDev-client-app.svg?branch=master)](https://travis-ci.org/Azure-Samples/iot-hub-SparkFun-ThingDev-client-app)

> This repo contains the source code to help you get familiar with Azure IoT using the Azure IoT SparkFun ESP8266 Thing-Dev Starter Kit. You will find the [lesson-based tutorials on Azure.com](https://docs.microsoft.com/azure/iot-hub/iot-hub-sparkfun-esp8266-thing-dev-get-started).

This repo contains an arduino application that runs on board SparkFun ESP8266 Thing-Dev with a DHT22 temperature&humidity sensor, and then sends these data to your IoT hub. At the same time, this application receives Cloud-to-Device message from your IoT hub, and takes actions according to the C2D command. 

## Prepare your Azure IoT Hub
You can follow [this page](https://docs.microsoft.com/azure/iot-hub/iot-hub-sparkfun-esp8266-thing-dev-get-started) to create your Azure IoT hub and register your device.

## Install board with your Arduino IDE
1. Start Arduino and open Preferences window.
2. Enter `http://arduino.esp8266.com/stable/package_esp8266com_index.json` into Additional Board Manager URLs field. You can add multiple URLs, separating them with commas.
3. Open Boards Manager from `Tools > Board` menu and install esp8266 platform 2.2.0 or later.
4. Select your ESP8266 board from `Tools > Board` menu after installation.

## Install libraries
Install the following libraries from `Sketch -> Include library -> Manage libraries`

* AzureIoTHub
* AzureIoTUtility
* AzureIoTProtocol_MQTT
* ArduinoJson
* DHT sensor library
* Adafruit Unified Sensor

## Connect your sensor with your board
### Connect with a physical DHT22 sensor
You can follow the image to connect your DHT22 with your SparkFun ESP8266 Thing-Dev.

![DHT22](https://docs.microsoft.com/en-us/azure/iot-hub/media/iot-hub-sparkfun-thing-dev-get-started/15_connections_on_breadboard.png)

### DON'T HAVE A PHYSICAL DHT22?
You can use the application to simulate temperature&humidity data and send to your IoT hub.
1. Open the `app/config.h` file.
2. Change the `SIMULATED_DATA` value from `false` to `true`.

## Configure and run sample application
Upload the `app.ino` to your board.

### Input your credential information
After you successfully upload the code to your board. You will see some prompt, input your credential information according to the prompts.

### Send Cloud-to-Device command
You can send a C2D message to your device. You can see the device prints out the message and blinks once receiving the message.

### Send Device Method command
You can send `start` or `stop` device method command to your Pi to start/stop sending message to your IoT hub.
