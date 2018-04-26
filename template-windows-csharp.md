| **platform** | **device** | **language** |
| --- | --- | --- |
|

| **Windows 10 Enterprise** |
| --- |

  |

| **ASTUT-W155-PC1S** |
| --- |

  | **Csharp** |

##
# Run a simple Csharp sample on

# ASTUT-W155-PC1S

# device running Windows 10

##
# Table of Contents

- [Introduction](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/iotcertification/templates/template-windows-csharp.md#Introduction)
- [Step 1: Prerequisites](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/iotcertification/templates/template-windows-csharp.md#Prerequisites)
- [Step 2: Prepare your Device](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/iotcertification/templates/template-windows-csharp.md#PrepareDevice)
- [Step 3: Build and Run the Sample](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/iotcertification/templates/template-windows-csharp.md#Build)
- [Next Steps](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/iotcertification/templates/template-windows-csharp.md#NextSteps)

##
# Introduction

**About this document**

This document describes how to connect {enter your device name here} device running Windows10 with Azure IoT SDK. This multi-step process includes:

- Configuring Azure IoT Hub
- Registering your IoT device
- Build and deploy Azure IoT SDK on device

##
# Step 1: Prerequisites

You should have the following items ready before beginning the process:

- [Prepare your development environment](https://github.com/Azure/azure-iot-sdk-csharp/blob/master/doc/devbox_setup.md)
- [Setup your IoT hub](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/setup_iothub.md)
- [Provision your device and get its credentials](https://github.com/Azure/azure-iot-device-ecosystem/blob/master/manage_iot_hub.md)
- ASTUT-W155-PC1S device.

##
# Step 2: Prepare your Device

##
# Install Windows 10 Enterprise LTSB on ASTUT-W155-PC1S

- Create a bootable USB Drive. Please follow this guide on how to create a bootable drive ( [https://www.microsoft.com/download/windows-usb-dvd-download-tool](https://www.microsoft.com/download/windows-usb-dvd-download-tool)).
- Insert the bootable USB Drive from the previous step into your ASTUT-W155-PC1S. Turn on your ASTUT-W155-PC1S device and press the  **Delete**  key.
- Change the BIOS Boot option filter to &quot; **Boot&quot;**.
- Change the &quot; **Boot Option Priorities&quot;**  to boot from your USB Drive.
- Save changes and restart your ASTUT-W155-PC1S. Follow on screen instructions to install Windows Operating System on your ASTUT-W155-PC1S.
- When Windows 10 install completed, remember [change to developer mode](https://blogs.msdn.microsoft.com/devschool/2015/05/06/windows-10-setting-the-developer-mode/).

##
# Step 3: Build and Run the sample

- Download the [Azure IoT SDK](https://github.com/Azure/azure-iot-sdk-csharp) and the sample programs and save them to your local repository.
- Open a device console (command prompt or a powershell window) and change to your local SDK **azure-iot-sdk-csharp** directory.
- Add the Iot Hub device connection string on your device as an environment variable:
-  setx IOTHUB\_DEVICE\_CONN\_STRING &lt;yourDeviceConnectionString&gt;
- Add &quot;BuildProject security\tpm\samples &quot;SecurityProvider for TPM Samples&quot;&quot; to if(-not $nobuild) in build.ps1
- Run the following command to build the SDK:
-  build.cmd -config Release
- From the device console, run the sample using following command:

**If HTTP protocol:**

  cd iothub\device\samples\DeviceClientHttpSample\bin\Release\netcoreapp2.0

  dotnet DeviceClientHttpSample.dll

**If MQTT protocol:**

  cd iothub\device\samples\DeviceClientMqttSample\bin\Release\netcoreapp2.0

  dotnet DeviceClientMqttSample.dll

**If AMQP protocol:**

  cd iothub\device\samples\DeviceClientAmqpSample\bin\Release\netcoreapp2.0

  dotnet DeviceClientAmqpSample.dll

- Use the **DeviceExplorer** utility to observe the messages IoT Hub receives from the **Device Client Sample** application.
- Refer &quot;Monitor device-to-cloud events&quot; in [DeviceExplorer Usage document](https://github.com/Azure/azure-iot-sdk-csharp/blob/master/tools/DeviceExplorer/doc/how_to_use_device_explorer.md) to see the data your device is sending.
- Refer &quot;Send cloud-to-device messages&quot; in [DeviceExplorer Usage document](https://github.com/Azure/azure-iot-sdk-csharp/blob/master/tools/DeviceExplorer/doc/how_to_use_device_explorer.md) for instructions on sending messages to device.

##
# Next Steps

You have now learned how to run a sample application that collects sensor data and sends it to your IoT hub. To explore how to store, analyze and visualize the data from this application in Azure using a variety of different services, please click on the following lessons:

- [Manage cloud device messaging with iothub-explorer](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-explorer-cloud-device-messaging)
- [Save IoT Hub messages to Azure data storage](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-store-data-in-azure-table-storage)
- [Use Power BI to visualize real-time sensor data from Azure IoT Hub](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-power-bi)
- [Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-web-apps)
- [Weather forecast using the sensor data from your IoT hub in Azure Machine Learning](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-weather-forecast-machine-learning)
- [Remote monitoring and notifications with Logic Apps](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps)