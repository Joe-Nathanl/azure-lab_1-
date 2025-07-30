Part 1. Set up Azure Subscription

Created A new Azure subscription for the process 

<img width="1538" height="740" alt="image" src="https://github.com/user-attachments/assets/57c563ba-fb74-4af1-ab4a-ed1ad604d45d" />



Part 2. Create the Honey Pot (Azure Virtual Machine)


A. Create a resource group to hold everything 




<img width="662" height="572" alt="image" src="https://github.com/user-attachments/assets/df886b58-53f8-4462-89eb-ae89e10da018" />


B. Next, I created a Virtual Network or VNET to host my virtual machine (The Honey Pot).




<img width="676" height="580" alt="image" src="https://github.com/user-attachments/assets/72167a31-4b5a-4296-9fd9-45d4e127e13e" />







C. Lastly, I created a virtual machine 

<img width="655" height="564" alt="image" src="https://github.com/user-attachments/assets/81dfba6b-a653-4bc2-9ecb-46b2dc4543e6" />







Steps to turn the system into a Honey Pot 



  A.  I navigated to Network Security to make a new rule allowing any traffic into the network. This is necessary to make a tempting Honey Pot.

<img width="1887" height="766" alt="image" src="https://github.com/user-attachments/assets/ee9b2365-beaf-495f-802f-1de7f9d2f8c6" />




B. Next, I logged into my virtual network and turned off Windows Firewall using the wf.msc menu. 


<img width="1276" height="912" alt="image" src="https://github.com/user-attachments/assets/40dfa8d9-363c-48a8-ac80-715342d5a6d0" />



<img width="986" height="489" alt="image" src="https://github.com/user-attachments/assets/45d6d2bc-f8b0-4f76-8f9a-49ee78aa8068" />


This Machine is now a Complete Honey Pot



Part 3: Logging and visualizing everything




We will achieve this by log Forwarding and KQL


Create a Sentinel Instance and connect it to Log Analytics


Create Log Analytics Workspace

<img width="381" height="593" alt="image" src="https://github.com/user-attachments/assets/c6c0c52c-0a62-4626-8cc0-16f3459a37a5" />









nfigure the “Windows Security Events via AMA” connector

Create the DCR within Sentinel, watch for extension creation

Query for logs within the LAW





We can now query the Log analytics workspace as well as the SIEM, Sentinel directly, which we will do soon


Using KQL, I observed the logs of my VM:

SecurityEvent
| where EventId == 4625

<img width="1252" height="549" alt="image" src="https://github.com/user-attachments/assets/8bcf5928-1f5e-4b8b-95b6-5e8dec5d687e" />


Quite a few Security Violations! 











