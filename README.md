# 03_Phishing-Investigation

## MITRE ATT&CK
- T1566.002 - Spearphishing Link

## Objective

Investigate a suspected phishing email reported by a user after they downloaded and opened a malicious attachment disguised as a payslip.

## Environment

- Windows endpoint
- Wazuh
- Sysmon
- Email client
- Controlled lab environment

## Scenario

A user reported receiving what appeared to be a legitimate payslip email.

The user later noticed something unusual about the email and reported it to the SOC. However, the user had already downloaded and opened the attached file.

After opening the file, the user reported unusual behaviour on the workstation, including intermittent screen flashing.

The investigation focuses on determining whether the email and downloaded file are suspicious and identifying relevant endpoint activity following execution.

## Investigation Flow

1. Review the user-reported phishing email
2. Examine email headers and sender information
3. Analyse the attachment and identify relevant indicators
4. Review Wazuh alerts and Sysmon telemetry
5. Correlate endpoint activity with the reported execution time
6. Assess whether the activity is malicious or suspicious
7. Determine the appropriate L1 disposition
8. Escalate to L2 for further investigation

## Outcome

- **Finding:** Suspected malicious phishing email and attachment
- **Disposition:** Escalated to L2
- **Key evidence:** Suspicious attachment, email indicators, and endpoint activity following execution

## Report

[View the investigation report](investigation-report.md)

## Medium Post

[View the investigation in detail](https://medium.com/@larry.kaheiwong/investigating-a-phishing-email-from-user-report-to-l1-escalation-9cafaf69ab82)
