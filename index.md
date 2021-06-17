---
title: Cloud Setup
layout: template
filename: index
---
# MxB TV Cloud Setup Using Azure Hybrid Connection Instructions

## How Azure Hybrid Connection Works {.tabset}

Hybrid Connections requires a relay agent to be deployed where it can reach both the desired endpoint as well as to Azure.
The relay agent, Hybrid Connection Manager (HCM), calls out to Azure Relay over port 443.
From the web app site, the App Service infrastructure also connects to Azure Relay on your application's behalf.
Through the joined connections, your app is able to access the desired endpoint.
The connection uses TLS 1.2 for security and shared access signature (SAS) keys for authentication and authorization.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-connectiondiagram.png)
When your app makes a DNS request that matches a configured Hybrid Connection endpoint, the outbound TCP traffic will be redirected
through the Hybrid Connection.

### Empact IT Steps

# Add and Create Hybrid Connections in your app

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

## Get Gateway Connection String

Go to the hybrid connections page of your app and click on the hybrid connection you have just added.
Click on it and you will see the properties of the  hybrid connection.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-properties.png)

From the properties you will gate the gateway connection string to which will allow hybrid connection manager to access you hybrid connection.

### Client Steps

# Download and Set Up Hybrid Connection Manager
The Hybrid Connections feature requires a relay agent in the network that hosts your Hybrid Connection endpoint. That relay agent is called the Hybrid Connection Manager (HCM).

This tool runs on Windows Server 2012 and later. The HCM runs as a service and connects outbound to Azure Relay on port 443.

To download click on the link below.

* [Download Link](https://download.microsoft.com/download/0/E/4/0E48D57B-C563-4877-8ACB-CB740C7C6A78/HybridConnectionManager.msi)

## Manually add a Hybrid Connection
To enable someone outside your subscription to host an HCM instance for a given Hybrid Connection for instance Empactit they will have to send over a connection string that's been mapped to a specified service i.e. HOST `mxb44.empactit.com` on PORT `8080`. To use that string, select Enter Manually in the HCM, and paste in the gateway connection string.

![Manually add a connection string](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-manual.png)
