---
published: false
---
## Connecting a treadmill to the IBM Cloud IoT Platform

Continuing from the previous blogs, I will explain how to connect a treadmill as a sensor within the IBM Cloud IoT Platform.

First we need to create a "Internet of Things Platform Starter" kit within [https://cloud.ibm.com/catalog?search=Internet%20of%20things&category=starterkits](https://cloud.ibm.com/catalog?search=Internet%20of%20things&category=starterkits)
In order to do this you will need an IBM Cloud account. You can just signup for a free Lite account, no credit card required.
The starter kit contains the Internet of Things services as well as a Cloudant Database and a Node-Red runtime, which we will later use to create some dashboards.

![IBM_IoT_Platform_Create.png]({{site.baseurl}}/images/IBM_IoT_Platform_Create.png)

Next, I created a device type "ESP32" and a device "ESPRESSIF" (you can pick whatever names you want here). When creating a device you can provide your own authentication token or you can let the system generate one for you. I prefer to set my own, which makes it easier to remember afterwords.

![IBM_IoT_Device_Create.png]({{site.baseurl}}/images/IBM_IoT_Device_Create.png)


Basically, that's all we need to setup in the IoT platform.
Next we need to adapt the Arduino code to make a connection the IBM IoT service using MQTT.
You can find the code [here](Treadmill-Bluetooth-IoT/Treadmill_BLE_IBM_MQTT/Treadmill_BLE_IBM_MQTT.ino)

