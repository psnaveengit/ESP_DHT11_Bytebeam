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


8.	Go to Dashboard Option. Create a new dashboard. Click and open that dashboard
9.	On top right corner, click the “Panel” option & select Line Graph
10.	Create 2 Panels like this for Temperature & humidity, each configured as shown below 

![temp](https://user-images.githubusercontent.com/104820561/211803192-a8427ff8-399d-4d2b-8b67-f3e5314809ba.png)
![hum](https://user-images.githubusercontent.com/104820561/211803224-64754804-4ccc-470d-ab48-62eba24776c1.png)

11.	Make sure to save the dashboard by clicking the save button
![dashboard](https://user-images.githubusercontent.com/104820561/211804514-0f921c25-4b0a-492e-b01f-6e72ede61b38.png)

12. Make sure to set the Dashboard Refresh Rate too. By default it may not be set and hence the dashboard will be static. Set it to Refresh every 5 Seconds.
![dashboard2](https://user-images.githubusercontent.com/104820561/211807372-2964d8d1-dae7-4990-a1a3-effd042a3f92.png)


13. Now you are ready to build, flash and monitor the code on to ESP32. Once done lets see the results:
14. Results are below. I just blowed air on top of the sensor to change the readings

![results](https://user-images.githubusercontent.com/104820561/211807814-6d8a973d-eea6-464a-8087-e366e81f7079.png)


## Conclusion: 
That is the end of this project. We have just scratched the surface of what Bytebeam can do.Intention of this short tutorial is to just get you started with how to integreate bytebeam sdk with your own project. As the Project is simple, I didn't dive into code explanation. You can checkout official bytebeam docs to see APIs and how to use them. There are a lot of other cool features that Bytebeam offers which is not covered here. Feel free to explore and make your own projects utilizing all these features.


# Credits/Acknowledgments:
1. Bytebeam SDK: https://github.com/bytebeamio/esp-bytebeam-sdk
2. DHT11 Sensor Driver: https://github.com/UncleRus/esp-idf-lib
3. Bytebeam Docs: https://bytebeam.io/docs/esp-idf
4. Help from Bytebeam Team member: https://github.com/mayankbytebeam

