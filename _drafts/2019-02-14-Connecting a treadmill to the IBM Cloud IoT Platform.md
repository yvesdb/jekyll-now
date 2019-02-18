---
published: false
---
## Connecting a treadmill to the IBM Cloud IoT Platform

Continuing from the previous blogs, I will explain how to connect a treadmill as a sensor within the IBM Cloud IoT Platform.

First we need to create a "Internet of Things Platform Starter" kit within [https://cloud.ibm.com/catalog?search=Internet%20of%20things&category=starterkits](https://cloud.ibm.com/catalog?search=Internet%20of%20things&category=starterkits)
In order to do this you will need an IBM Cloud account. You can just signup for a free Lite account, no credit card required.
The starter kit contains the "Internet of Things" service as well as a "Cloudant" Database and a "Node-Red" runtime, which we will later use to create some dashboards.

![IBM_IoT_Platform_Create.png]({{site.baseurl}}/images/IBM_IoT_Platform_Create.png)

Next, launch the "Internet of Things Platform" service, create a device type "ESP32" and a device "ESPRESSIF" (you can pick whatever names you want here). When creating a device you can provide your own authentication token or you can let the system generate one for you. I prefer to set my own, which makes it easier to remember afterwords.

![IBM_IoT_Device_Create.png]({{site.baseurl}}/images/IBM_IoT_Device_Create.png)

One additional setting we need to do is to set the Security Level to "TLS Optional" within the IoT platform service since we're not using any encrypted communication.

Basically, that's all we need to setup within the IoT platform.
Next we need to adapt the Arduino code to make a connection the IBM IoT service using MQTT.
You can find the code [here](Treadmill-Bluetooth-IoT/Treadmill_BLE_IBM_MQTT/Treadmill_BLE_IBM_MQTT.ino)
Just update the MQTT parameters and the Wifi credentials and upload the code to the ESP32 module using the Arduino editor.
As soon as the ESP32 restarts, you should see the "ESP32" device active within the IBM Cloud IoT dashboard and once the treadmill gets started you should see the JSON payloads coming in.

![IBM_IoT_Device_Connected.png]({{site.baseurl}}/images/IBM_IoT_Device_Connected.png)


Now that we have the treadmill connected we can start using Node-Red in order to make a dashboard with some gauges and graphs representing the running distance as well as the belt speed and some calculated pace values.

![Treadmill_Dashboard.png]({{site.baseurl}}/images/Treadmill_Dashboard.png)








