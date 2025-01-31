SOC Automation Lab Setup

Introduction

Working in Security Operation Centers (SOC) can be daunting. Triage of every ticket or alert is time-consuming and, at times, mundane. But what if we can automate this process? Yes, we can automate these tasks using SIEM tools and open-source intelligence.

This overview dives into the process and steps to create a SOC automation lab in a virtualization environment.

Tools

	• Windows 10: Client
	• Ubuntu 24 Server: Wazuh Manager Server
	• Ubuntu 22 Server: The Hive
	• Shuffle: Automation Workflow
	• VirusTotal: IOC Enrichments 


Flow Chart

	1. Wazuh Manager
		○ Create Alerts
		○ Receive Events
		○ Perform Responsive Actions
	2. Shuffle
		○ Send Actions
		○ OSINT IOCs
		○ Send Email
	3. The Hive
		○ Receive Emails
	4. SOC Analyst
		○ Send Actions
	5. Router
		○ Send Events
	6. Windows 10 Wazuh Agent
		○ Receive Actions
		○ Send Alerts
  
![image](https://github.com/user-attachments/assets/85e73779-609e-437c-9766-7916855f3235)



Workflow

	1. Windows 10 clients send logs to the Wazuh Manager.
	2. The Wazuh Manager creates alerts based on attributes.
	3. The Wazuh Manager sends alerts to Shuffle.
	4. Shuffle extracts IOCs and checks on VirusTotal or other OSINT tools.
	5. Alerts are sent to The Hive, and an email is sent to the SOC analyst.
	6. The SOC analyst performs a check on the alert, then a responsive action is performed.

