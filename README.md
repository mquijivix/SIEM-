# SIEM- Building a Custom SIEM with Elastic 
![Elastics SIEM)]()


## Introduction

In this guide, I'll walk you through the steps to set up a customizable home lab for Elastic Stack Security Information and Event Management (SIEM) using the Elastic Web portal and a Kali Linux VM. You will learn how to generate security events on the Kali VM, set up an agent to forward data to the SIEM, query and analyze logs within the SIEM environment, and create custom alerts to enhance security monitoring

- Virtual Box  
-  Kali Linux
-  Elastic 


## Setting up the Agent to Collect Logs 
In Elastic SIEM, an agent is a software program installed on devices like servers or endpoints to collect and send data for centralized analysis and monitoring of security events. To integrate an agent with your Elastic SIEM instance, follow these steps:

Log in to your Elastic SIEM instance and access the Integrations page.
Search for “Elastic Defend” and click on it to open the integration page.

On the integration page, click “Install Elastic Defend” and follow the provided instructions specific to installing the agent on your Kali Linux VM.

Ensure “Linux” is selected, then copy the command provided on the integration page to your clipboard.

Paste the copied command into the terminal (command line) of your Kali Linux VM to complete the installation process
![]()


## Generating Security Events on the Kali VM 
To ensure the agent is functioning correctly, you can validate it by generating security-related events on your Kali VM using tools like Nmap.

Next, initiate a scan on your Kali machine with the command: sudo nmap <vm-ip>. You can also scan your host machine if your Kali VM is on a 'bridged' network configuration.

These scans produce various security events, such as identifying open ports and services running on those ports. Conduct multiple Nmap scans to further test the agent's functionality.




## Querying for Security Events in the Elastic SIEM

Now that data from the Kali VM has been forwarded to the SIEM, we can proceed with querying and analyzing the logs within the SIEM environment.

Within your Elastic Deployment, navigate to the 'Logs' tab under 'Observability'

In the search bar, enter a query to filter the logs. For instance, to find logs related to Nmap scans, you can use a query like: event.action: "nmap_scan" OR process.args: "sudo".

Click the 'Search' button to execute the query. The search results will be displayed in a table.






![]()

![]()

![]()


## Create a Dashboard to Visualize the Events

In addition to querying logs directly, you can leverage the visualizations and dashboards within the SIEM app to conduct in-depth analysis and detect patterns or anomalies in the data. For instance, you can create a straightforward dashboard that displays a chronological count of security events over time





## Create an Alert

In a SIEM environment, alerts play a critical role in identifying security incidents promptly and initiating appropriate responses. These alerts are generated from predefined rules or custom queries, configured to trigger specific actions when certain conditions are met. In this tutorial, we'll guide you through creating an alert within the Elastic SIEM instance to detect Nmap scans, directing notifications to email alerts





## Conclusion

In this project, we successfully set up a home lab using Elastic Stack Security Information and Event Management (SIEM) and a Kali Linux VM. By following the step-by-step instructions, we were able to:

Create a free Elastic account and set up an Elastic Cloud instance.
Install and configure a Kali Linux VM using VirtualBox or VMware.
Install and configure the Elastic Agent on the Kali VM to forward logs to the Elastic SIEM.
Generate security events on the Kali VM using tools like Nmap.
Query and analyze the forwarded logs in the Elastic SIEM to identify security events.
Create a dashboard to visualize the security events over time.
Set up alerts in the Elastic SIEM to detect specific security incidents, such as Nmap scans.
This home lab offers an excellent opportunity to develop and enhance your skills in security monitoring and incident response with Elastic SIEM. Completing this project has provided you with practical, hands-on experience in configuring and managing a SIEM, a vital capability for any future security professional.
