# ESP32 DHT11 Bytebeam Integration

This Simple Project is aimed at people who want to try out Bytebeam ESP32 Client SDK. When exploring any new IoT Platform, it is important to start off with easy projects so that the user gets used to the platform and its SDK integration first and foremost. Hence, a very common & easy to integrate DHT11 Sensor is used.

## What is Bytebeam?

Bytebeam is a fully managed cloud platform that serves all cloud needs like device management, dashboard, handling actions, notifications & OTA updates.
Checkout the SDK here: https://github.com/bytebeamio/esp-bytebeam-sdk to read more about it.

## Hardware Used:
1. ESP32 Dev Kit V1
2. DHT11 Sensor Module (3 Pin Variant)

## Hardware Interfacing:
DHT11 VCC -----  ESP32 3V3\
DHT11 GND -----  ESP32 GND\
DHT11 DATA ----- ESP32 D23 (GPIO23)


## Software Setup:
1. Windows 10
2. Visual Studio Code + ESP IDF Extension Installed & Configured
3. ESP IDF Version – v4.4
4. Bytebeam SDK Version – Pull this commit for v4.4: https://github.com/bytebeamio/esp-bytebeam-sdk/tree/1d50a711355298a50845aa34f77a2cd1d672bf32
(Latest Main Branch of Bytebeam SDK is IDF v5 compatible, but it created errors, thus used the above older commit with IDF v4.4)


## SDK Test:
1. Setup up Bytebeam cloud: https://bytebeam.io/docs/getting-started-on-bytebeam-cloud
2. Follow this guide https://bytebeam.io/docs/setting-up-bytebeam-esp-sdk till end of Step 2 to finish Bytebeam account setup, & Provisioning of device
3. Monitor your ESP32 & see whether device provisioning is done
4.  Lets, first test if the example code is working. Go to examples folder of the SDK
### Note 1: Make Sure you have added the Bytebeam ESP SDK to the CMake Build System of ESP project:
Make sure you have followed this properly: https://bytebeam.io/docs/setting-up-bytebeam-esp-sdk#AOwgi
### Note 2: Make Sure you have set WiFi SSID & Password of your local router using menuconfig or by editing the sdkconfig file in the project folder
5. Build, & Flash the example code. Monitor the Code. Also Check the Device Management Tab on your Bytebeam Cloud. 
6. Under Device Shadow there will be text "LED is off" for "Status" 
7. This example upload can be used to test whether the provisioning was proper & device can connect to the bytebeam cloud with the device_config file downloaded earlier during the provision process

## ESP DHT11 Project:
1.	Download my project code from this repository.
2.	Copy the bytebeam sdk folder from inside the sdk repo -  “…esp-bytebeam-sdk/components/bytebeam_esp_sdk “  to “…ESP32_DHT11_Bytebeam/components/” folder
3.	Basically, you are adding the sdk folder as a component inside the current project 
4.	Set the WiFi SSID and password in the menuconfig or sdkconfig file
5.	Go to the CMakeLists file inside root project directory (not the one in the main folder), and add the correct path for the SDK. An example is commented inside
### Before Building & Flashing lets setup the Bytebeam Cloud to accept & collect the temperature & humidity reading and then show it on dashboard 
6.	Now we need to add temperature & humidity fields in the bytebeam “device_shadow” stream
7.	Click “Admin” on top right corner & then under “device_shadow” stream, add humidity & temperature as 2 separate column names. Set both Column types as Float32
	
![stream](https://user-images.githubusercontent.com/104820561/211802073-10f49d18-55ef-430d-b8b8-83239b34db4b.png)


# Credits/Acknowledgments:
1. Bytebeam SDK: https://github.com/bytebeamio/esp-bytebeam-sdk
2. DHT11 Sensor Driver: https://github.com/UncleRus/esp-idf-lib
3. Bytebeam Docs: https://bytebeam.io/docs/esp-idf
4. Help from Bytebeam Team member: https://github.com/mayankbytebeam

