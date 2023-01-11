# ESP32 DHT11 Bytebeam Integration

This Simple Project is aimed at people who want to try out Bytebeam ESP32 Client SDK. When exploring any new IoT Platform, it is important to start off with easy projects so that the user gets used to the platform and its SDK integration first and foremost. Hence, a very common & easy to integrate DHT11 Sensor is used.

## What is Bytebeam?

Bytebeam is a fully managed cloud platform that serves all cloud needs like device management, dashboard, handling actions, notifications & OTA updates.
Checkout the SDK here: https://github.com/bytebeamio/esp-bytebeam-sdk to read more about it.

## Hardware Used:
ESP32 Dev Kit V1
DHT11 Sensor Module (3 Pin Variant)

## Software Setup:
Windows 10
Visual Studio Code + ESP IDF Extension Installed & Configured
ESP IDF Version – v4.4
Bytebeam SDK Version – Pull this commit for v4.4: https://github.com/bytebeamio/esp-bytebeam-sdk/tree/1d50a711355298a50845aa34f77a2cd1d672bf32
(Latest Main Branch of Bytebeam SDK is IDF v5 compatible, but it created errors, thus used the above older commit with IDF v4.4)


## SDK Integration:
1. Setup up Bytebeam cloud: https://bytebeam.io/docs/getting-started-on-bytebeam-cloud
2. Follow this guide https://bytebeam.io/docs/setting-up-bytebeam-esp-sdk till end of Step 2 to finish Bytebeam account setup, & Provisioning of device
3. Monitor your ESP32 & see whether device provisioning is done
4.  Lets, first test if the example code is working. Go to examples folder of the SDK
### Note 1: Make Sure you have added the Bytebeam ESP SDK to the CMake Build System of ESP project:
Make sure you have followed this properly: https://bytebeam.io/docs/setting-up-bytebeam-esp-sdk#AOwgi
### Note 2: Make Sure you have set WiFi SSID & Password of your local router using menuconfig or by editing the sdkconfig file in the project folder
5. Build, & Flash the example code. Monitor the Code. Also Check the Device Management Tab on your Bytebeam Cloud. 


