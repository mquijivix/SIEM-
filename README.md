# SIEM- Building a Custom SIEM with Elastic 

![Building a Custom SIEM with Elastic copy.pdf](https://github.com/user-attachments/files/16041939/Building.a.Custom.SIEM.with.Elastic.copy.pdf)

## Introduction

In this guide, I'll lead you through setting up a personalized home lab for Elastic Stack Security Information and Event Management (SIEM) using the Elastic Web portal and a Kali Linux VM. I will display hands-on experience in generating security events on the Kali VM, configuring an agent to transmit data to the SIEM, analyzing logs within the SIEM environment, and crafting custom alerts to bolster security monitoring capabilities.

- Virtual Box  
-  Kali Linux
-  Elastic 




## Setting up the Agent to Collect Logs 
In Elastic SIEM, an agent serves as a software program installed on devices like servers or endpoints to gather and transmit data for centralized analysis and monitoring of security events. Here’s how I integrated an agent with my Elastic SIEM instance:

Logged in to my Elastic SIEM instance and navigated to the Integrations page.
Searched for “Elastic Defend” and clicked on it to access the integration page.
Clicked on “Install Elastic Defend” and followed the provided instructions tailored for installing the agent on my Kali Linux VM.
Selected “Linux”, then copied the command provided on the integration page to my clipboard.
Pasted the copied command into the terminal (command line) of my Kali Linux VM to complete the installation process.



[Installing Agent] ![Elastic Agent ](https://github.com/mquijivix/SIEM-/assets/173574799/3e8a1ae4-e878-44c5-b5bd-f0da53b9d53c)






## Generating Security Events on the Kali VM 
To ensure the agent is functioning correctly, I validated it by generating security-related events on the Kali VM using tools like Nmap.

Next, initiate a scan on the Kali machine with the command: sudo nmap <vm-ip>. You can also scan your host machine if your Kali VM is on a 'bridged' network configuration.

These scans produce various security events, such as identifying open ports and services running on those ports. I conducted multiple Nmap scans to further test the agent's functionality.



[Generating Security Event] 
![Trigger nmap ](https://github.com/mquijivix/SIEM-/assets/173574799/dbf83e19-0b16-4fda-814b-36ca738787ca)






## Querying for Security Events in the Elastic SIEM

Now that data from the Kali VM has been forwarded to the SIEM, I proceeded with querying and analyzing the logs within the SIEM environment.

Within the Elastic Deployment, navigate to the 'Logs' tab under 'Observability'

In the search bar, enter a query to filter the logs. For instance, to find logs related to Nmap scans, I used a query like: event.action: "nmap_scan" OR process.args: "sudo".

I clicked the 'Search' button to execute the query. The search results were displayed in a table.




[Qurying nmap] 

<img width="703" alt="nmap Querry " src="https://github.com/mquijivix/SIEM-/assets/173574799/edc017c5-0f4f-4302-9f8e-136cfd5e1ad4">





## Create a Dashboard to Visualize the Events

In addition to querying logs directly, I can leverage the visualizations and dashboards within the SIEM app to conduct in-depth analysis and detect patterns or anomalies in the data. For instance, I created a straightforward dashboard that displays a chronological count of security events over time.



[Setting up SIEM] 
![Custom SIEM Map ](https://github.com/mquijivix/SIEM-/assets/173574799/89a91049-9bdc-483d-9c23-57e95f34b3e2)






## Create an Alert

In a SIEM environment, alerts play a critical role in identifying security incidents promptly and initiating appropriate responses. These alerts are generated from predefined rules or custom queries, configured to trigger specific actions when certain conditions are met. I'll guide you through creating an alert within the Elastic SIEM instance to detect Nmap scans, directing notifications to email alerts.




[Custom Alert]


<img width="808" alt="Setting up Alert " src="https://github.com/mquijivix/SIEM-/assets/173574799/cf5f0723-3166-412b-b01e-c5d1fbd3fa57">








## Conclusion

In this project, I successfully set up a home lab using Elastic Stack Security Information and Event Management (SIEM) and a Kali Linux VM. By following the step-by-step instructions, I was able to:

Create a free Elastic account and set up an Elastic Cloud instance.
Install and configure a Kali Linux VM using VirtualBox or VMware.
Install and configure the Elastic Agent on the Kali VM to forward logs to the Elastic SIEM.
Generate security events on the Kali VM using tools like Nmap.
Query and analyze the forwarded logs in the Elastic SIEM to identify security events.
Create a dashboard to visualize the security events over time.
Set up alerts in the Elastic SIEM to detect specific security incidents, such as Nmap scans.
This home lab offers an excellent opportunity to develop and enhance skills in security monitoring and incident response with Elastic SIEM. Completing this project has provided me with practical, hands-on experience in configuring and managing a SIEM, a vital capability for any future security professional.
