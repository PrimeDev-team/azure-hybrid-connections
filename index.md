---
title: How Azure Hybrid Connection Works
layout: template
filename: index
--- 
# Azure Hybrid Connection Tutorial

## How Azure Hybrid Connection Works

Hybrid Connections requires a relay agent to be deployed where it can reach both the desired endpoint as well as to Azure. 
The relay agent, Hybrid Connection Manager (HCM), calls out to Azure Relay over port 443. 
From the web app site, the App Service infrastructure also connects to Azure Relay on your application's behalf. 
Through the joined connections, your app is able to access the desired endpoint. 
The connection uses TLS 1.2 for security and shared access signature (SAS) keys for authentication and authorization.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-connectiondiagram.png)
When your app makes a DNS request that matches a configured Hybrid Connection endpoint, the outbound TCP traffic will be redirected 
through the Hybrid Connection.
