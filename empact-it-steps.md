---
title: Empactit Steps
layout: template
filename: empact-it-steps
--- 

## Empactit Steps
### Add and Create Hybrid Connections in your app

To create a Hybrid Connection, go to the Azure portal and select your app. 
Select Networking > Configure your Hybrid Connection endpoints. Here you can see the Hybrid Connections that are configured for your app.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-portal.png)

To add a new Hybrid Connection, select [+] Add hybrid connection. You'll see a list of the Hybrid Connections that you already created within your subscription. 
Select the hybrid connection you need for your app and add them to your app.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-addhc.png)

If you want to create a new Hybrid Connection, select Create new hybrid connection. Specify the:

* Hybrid Connection name.
* Endpoint hostname.
* Endpoint port.
* Service Bus namespace you want to use.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-createhc.png)

### Get Gateway Connection String

Go to the hybrid connections page of your app and click on the hybrid connection you have just added.
Click on it and you will see the properties of the  hybrid connection.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-properties.png)

From the properties you will gate the gateway connection string to which will allow hybrid connection manager to access you hybrid connection.

