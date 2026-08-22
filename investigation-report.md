# Phishing Email Investigation

**Severity:** High

**Disposition:** Escalate to L2

**Tools:** Email client, Wazuh, Sysmon

## Alert

A user reported receiving a suspicious payslip email after downloading and opening the attached file. The user subsequently reported unusual workstation behaviour, including intermittent screen flashing.

## Evidence

| Indicator          | Finding                                                 |
| ------------------ | ------------------------------------------------------- |
| Sender address     | `mekemak123@gmail.com`                                  |
| Expected sender   | `makemak123@gmail.com`                                  |
| Return-Path        | `mekemak123@gmail.com`                                     |
| Target address       | `larry.kaheiwong@gmail.com`                                     |
| Timestamp          | Sat, 22 Aug 2026 11:34:34 +0100                         |
| SPF                | Pass                                                    |
| DKIM               | Pass                                                    |
| Download link      | `hxxp://10[.]0[.]2[.]4:8080/Payslip_August2026[.]pdf[.]exe` |
| File name          | `Payslip_August2026.pdf.exe`                            |
| Endpoint telemetry | Sysmon Event ID 11 file creation                        |

The email contains multiple suspicious indicators, including inconsistent sender information and a download link using a double-extension `.pdf.exe` filename. The link points to an IP address and non-standard port rather than a normal payslip/document delivery service.

SPF and DKIM both passed; however, these results alone do not establish that the email or its content is legitimate.

## Email Evidence

<img width="1147" height="398" alt="Suspicious-email" src="https://github.com/user-attachments/assets/09f7b2a0-a4e5-4ccd-8378-b6b33d931e12" />

## Endpoint Evidence

The user reported opening the downloaded file. Wazuh endpoint telemetry showed subsequent file creation activity through Sysmon Event ID 11.

<img width="1908" height="724" alt="Wazuh-file-creation" src="https://github.com/user-attachments/assets/a8b6eed4-6e98-473d-af36-5d09575cffed" />

## Assessment

The email is suspicious and contains indicators consistent with a phishing attempt. The user also reported opening the downloaded file and experiencing unusual workstation behaviour afterward.

Based on the available evidence, the case was escalated to L2 for further investigation.

## Disposition

**Escalate to L2**

### Recommended L2 Actions

* Analyse the downloaded file safely.
* Determine whether the file executed successfully.
* Review process creation and child-process activity around the execution time.
* Review network connections associated with the endpoint.
* Determine whether the endpoint requires containment.
* Investigate whether other users received the same phishing email.
