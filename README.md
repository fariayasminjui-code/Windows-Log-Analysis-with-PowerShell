**Windows Log Analysis with PowerShell**

**About This Lab**

This repository contains my practical work for Week 4 Lab: Windows Log Analysis with PowerShell.
In this lab, I explored how Windows Security Event Logs can be used to investigate login activities and understand suspicious behavior on a Windows system. I used PowerShell commands to retrieve, filter, and examine event log data.
The main goal was to develop my practical skills in Windows log analysis and understand how security analysts investigate events during an incident.

**Lab Objectives**

Retrieve Windows Security Event Logs using PowerShell.
Filter events by specific Event IDs and time ranges.
Investigate successful and failed login attempts.
Extract useful information from event log records.
Understand how repeated failed logins may indicate a brute-force attempt.
Explore how Windows logs can support the investigation of suspicious activities.
Practice writing PowerShell commands and scripts for security log analysis.

**Tools and Environment**

**Operating System:** Windows 10/11
**Shell:** Windows PowerShell
**Log Source:** Windows Security Event Log
**Main Command:** Get-WinEvent

**Tasks and Practical Work**

**1. Retrieving Windows Security Logs**
I used the Get-WinEvent cmdlet to retrieve recent events from the Windows Security log and examine the available event information.

Example command:
Get-WinEvent -LogName Security -MaxEvents 10

**2. Analyzing Successful Login Attempts**
I explored Event ID 4624, which records successful logon events. This helped me understand how login activity can be reviewed during a security investigation.

**3. Investigating Failed Login Attempts**
I examined Event ID 4625, which records failed logon attempts. These events can help an analyst investigate repeated authentication failures and potentially suspicious login behavior.

**4. Filtering Security Events**
I practiced filtering event logs by Event ID and retrieving relevant records instead of reviewing every event manually.

Example command:
Get-WinEvent -FilterHashtable @{
    LogName = 'Security'
    ID = 4625
} -MaxEvents 10

**5. Extracting Event Information**
I practiced extracting useful details from event records, such as:

Event timestamp
Event ID
Username-related information
Source IP information, when available
Logon type
Event message

The available information depends on the event and the fields recorded in the system log.

**6. Understanding Suspicious Login Patterns**
I explored how multiple failed logins can help identify activity that may require further investigation. Repeated failures alone do not prove a brute-force attack, so event details and surrounding activity must also be considered.

**7. Exploring Additional Security Events**
The lab also introduces the use of Windows event logs to investigate other potentially suspicious activities, including lateral movement and privilege escalation.

Examples of relevant Event IDs include:

**4648:** A logon was attempted using explicit credentials.
**5140:** A network share was accessed.
**4732:** A member was added to a security-enabled local group.
**4672:** Special privileges were assigned to a new logon.

These events require context before drawing conclusions about whether an activity is malicious.

**Screenshots**

The Screenshots/ folder contains screenshots of my PowerShell commands and their outputs from the lab.
These screenshots document the practical steps and results of the exercises.

**Repository Structure**

Windows-Log-Analysis-with-PowerShell/
│
├── README.md
│
├── Screenshots/
│   └── PowerShell command and output screenshots
│
├── Scripts/
│   ├── Analyze-SecurityLogs.ps1
│   └── Detect-BruteForce.ps1
│
└── Reports/
    └── Windows-Log-Analysis-Report.md

**What I Learned**

Through this lab, I developed a better understanding of:
Windows Security Event Logs
PowerShell commands for retrieving and filtering logs
Successful and failed authentication events
Extracting useful information from event records
Recognizing suspicious patterns that may require further investigation
The role of log analysis in security monitoring and incident investigation

**Disclaimer**

This repository is intended for educational and defensive cybersecurity learning. Log analysis should only be performed on systems and data that I am authorized to access.

**Author**
**Faria Yasmin Jui**

Student at University of Frontier Technology, Bangladesh
Department of Cybersecurity Engineering
