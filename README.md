# Azure-Honeyport-Threat-Monitoring-Project
Azure Honeyport Threat Monitoring Project
 Overview
This project demonstrates the deployment of a Honeyport in Azure to detect unauthorized login attempts. Logs were collected using Azure Log Analytics and monitored through Microsoft Sentinel to detect suspicious IP activity and brute-force attempts.

The goal was to simulate attacker behavior and build detection rules using KQL queries.

## Azure Honeyport Threat Detection Architecture

The diagram below illustrates how attacker activity flows through Azure logging infrastructure into Microsoft Sentinel for detection, alerting, and investigation.

<img width="873" height="670" alt="image" src="https://github.com/user-attachments/assets/661d58d1-a346-4a71-9acf-8c789d972d88" />


# What Was Implemented
Configured a honeyport to attract unauthorized login attempts

Enabled log collection via Data Collection Rule

Created KQL queries to detect:

Failed login attempts

Successful login attempts

Suspicious IP behavior

Built Analytics Rules for automated alert generation

Created dashboard for monitoring activity

Investigated public IP addresses attempting access

# Sample KQL Query (Failed Logins)
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts = count() by IPAddress, Account
| order by FailedAttempts desc

 # IP Investigation
Example IP investigated:

129.212.227.238

Identified as a Public IP address

Checked reputation via public IP lookup services
# Project ScreenShot
<img width="940" height="459" alt="image" src="https://github.com/user-attachments/assets/8f94f65d-b0cd-412f-951e-b60734b8ed51" />

<img width="940" height="424" alt="image" src="https://github.com/user-attachments/assets/4bf818c6-d308-49ae-8905-8ce9a146935e" />
<img width="940" height="426" alt="image" src="https://github.com/user-attachments/assets/c3a8d510-ac98-49ea-b802-e631bc013d2c" />
<img width="940" height="445" alt="image" src="https://github.com/user-attachments/assets/6bcbe59a-56b0-408b-b0fa-585f6ed360d4" />
<img width="940" height="607" alt="image" src="https://github.com/user-attachments/assets/6c8a9a6b-7b07-43d9-a255-faa7fb507634" />
<img width="940" height="442" alt="image" src="https://github.com/user-attachments/assets/10b876aa-610f-48c8-aa67-bd87f916211a" />
<img width="940" height="387" alt="image" src="https://github.com/user-attachments/assets/e862919c-a20e-4917-a67b-91e495d53cec" />
<img width="940" height="429" alt="image" src="https://github.com/user-attachments/assets/64c4cc7d-761d-4c5f-a509-6e71b2dae242" />
<img width="940" height="429" alt="image" src="https://github.com/user-attachments/assets/02eb83b4-5f9b-4c92-a52a-6819dfe9aded" />
<img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/dee1c68b-5603-44e6-8061-913807161ef7" />
<img width="940" height="455" alt="image" src="https://github.com/user-attachments/assets/5faa6a98-fc09-42ae-934a-69d63e47842d" />
<img width="940" height="374" alt="image" src="https://github.com/user-attachments/assets/57532bab-1ca1-4ef4-a1aa-0fd383f7fe0e" />
<img width="940" height="427" alt="image" src="https://github.com/user-attachments/assets/41edd6a4-c746-408e-962e-f14bbbb5424e" />




 # Key Findings
Multiple failed login attempts from public IP ranges

Evidence of automated scanning activity

Successful detection using Microsoft Sentinel analytics rules

# Dashboard Capabilities
Real-time login monitoring

Suspicious IP detection

Alert-based investigation workflow

# Lessons Learned
Importance of log visibility

How brute-force attacks appear in logs

Writing efficient KQL detection rules

Building alert-driven SOC workflows

# Future Improvements
Integrate threat intelligence feeds

Automate IP blocking using playbooks

Deploy multiple honeyports

Add GeoIP enrichment
