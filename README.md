# 03_Phishing-Investigation
Objective:
Investigate repeated failed RDP authentication followed by successful authentication using Wazuh.

## Environment:
- Windows endpoint
- Wazuh
- Sysmon
- Email client
- Controlled lab environment

## Scenario:

User reported receiving what appeared to be a legitimate payslip email
              
The user later noticed something was unusual about the email and reported it to the SOC. However, the user had already downloaded and opened the attached file.

After opening the file, the user reported unusual behaviour on the workstation, including intermittent screen flashing.

The investigation focuses on determining whether the email and downloaded file are suspicious and identifying relevant endpoint activity following execution.

## Report

[View the investigation report](investigation-report.md)
