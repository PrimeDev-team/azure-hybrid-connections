---
title: Client Steps
layout: template
filename: client-steps
--- 

## Client Steps

### Download and Set Up Hybrid Connection Manager
The Hybrid Connections feature requires a relay agent in the network that hosts your Hybrid Connection endpoint. That relay agent is called the Hybrid Connection Manager (HCM). 

This tool runs on Windows Server 2012 and later. The HCM runs as a service and connects outbound to Azure Relay on port 443.

To download click on the link below.

* [Download Link](https://download.microsoft.com/download/0/E/4/0E48D57B-C563-4877-8ACB-CB740C7C6A78/HybridConnectionManager.msi)

### Manually add a Hybrid Connection
To enable someone outside your subscription to host an HCM instance for a given Hybrid Connection for instance Empactit they will have to send over a connection string that's been mapped to a specified service i.e. HOST `mxb44.empactit.com` on PORT `8080`. To use that string, select Enter Manually in the HCM, and paste in the gateway connection string.

![Manually add a connection string](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-manual.png)
