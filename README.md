
## How Azure Hybrid Connection Works

Hybrid Connections requires a relay agent to be deployed where it can reach both the desired endpoint as well as to Azure. 
The relay agent, Hybrid Connection Manager (HCM), calls out to Azure Relay over port 443. 
From the web app site, the App Service infrastructure also connects to Azure Relay on your application's behalf. 
Through the joined connections, your app is able to access the desired endpoint. 
The connection uses TLS 1.2 for security and shared access signature (SAS) keys for authentication and authorization.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-connectiondiagram.png)
When your app makes a DNS request that matches a configured Hybrid Connection endpoint, the outbound TCP traffic will be redirected 
through the Hybrid Connection.

## Add and Create Hybrid Connections in your app

To create a Hybrid Connection, go to the Azure portal and select your app. 
Select Networking > Configure your Hybrid Connection endpoints. Here you can see the Hybrid Connections that are configured for your app.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-portal.png)

To add a new Hybrid Connection, select [+] Add hybrid connection. You'll see a list of the Hybrid Connections that you already created. 
To add one or more of them to your app, select the ones you want, and then select Add selected Hybrid Connection.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-addhc.png)

If you want to create a new Hybrid Connection, select Create new hybrid connection. Specify the:

* Hybrid Connection name.
* Endpoint hostname.
* Endpoint port.
* Service Bus namespace you want to use.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-createhc.png)

## Download and Setup Hybrid Connection Manager
The Hybrid Connections feature requires a relay agent in the network that hosts your Hybrid Connection endpoint. That relay agent is called the Hybrid Connection Manager (HCM). To download HCM, from your app in the Azure portal, select Networking > Configure your Hybrid Connection endpoints.

This tool runs on Windows Server 2012 and later. The HCM runs as a service and connects outbound to Azure Relay on port 443.

## Add the Hybrid Connection to Hybrid Connection Manager
Click on the add a new hybrid connection button.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-hcm.png)

You will then be asked to login to your azure account after successfull login you will be redirected to the 
screen below.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-hcmadd.png)

Select the relevant subscription and you will see the connection you created in the 
above steps.
Select the connections you want the connection manager to relay and save

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-hcmadded.png)

You can now see the Hybrid Connections you added. You can also select the configured Hybrid Connection to see details.

![alt text](https://docs.microsoft.com/en-us/azure/app-service/media/app-service-hybrid-connections/hybridconn-hcmdetails.png)
