<div align="center">

![Possible Logon Breach Investigation](assets/banner.svg)

# Possible Logon Breach Investigation

**Defender Advanced Hunting validation of successful external RDP access**

[![Live Case Study](https://img.shields.io/badge/Live%20Case%20Study-Open-22c55e?style=for-the-badge)](https://grhmmckean33.github.io/soc-rdp-logon-breach-investigation/) [![PDF Report](https://img.shields.io/badge/PDF%20Report-View-dc2626?style=for-the-badge)](report/SOC_Investigation_Report_Possible_Logon_Breach.pdf)

</div>

## Case study overview

A high-severity authentication investigation that used Microsoft Defender Advanced Hunting to turn an initially uncertain logon alert into an evidence-backed RDP timeline. The investigation confirmed external TCP/3389 connections, successful NTLM authentication and a subsequent RemoteInteractive administrator session.

| Area | Detail |
| --- | --- |
| Severity | **High** |
| Assessment | **True Positive - Successful External RDP Logon - High Confidence** |
| Environment | Maple Tax Solutions (MTS) |
| MITRE ATT&CK | T1110 - Brute Force (Defender alert mapping) |
| Full case study | **[View GitHub Pages site](https://grhmmckean33.github.io/soc-rdp-logon-breach-investigation/)** |
| Investigation report | **[Open PDF](report/SOC_Investigation_Report_Possible_Logon_Breach.pdf)** |

## Key findings

- 176.53.159[.]230 established an accepted inbound RDP connection and successfully authenticated as mts\administrator at 10:23:40 UTC.
- 176.53.159[.]222 later established another accepted RDP connection followed by successful NTLM logons and a RemoteInteractive session.
- Post-logon process review showed normal RDP/session activity; a targeted hunt for common command-line and administrative tools returned no results in the reviewed period.
- The report confirms successful external RDP access while keeping authorisation and human-operator attribution unresolved.

## Investigation approach

- Used DeviceLogonEvents to validate authentication result, account, protocol, logon type and source IP.
- Used DeviceNetworkEvents to confirm inbound TCP/3389 activity and RDP service handling.
- Used DeviceProcessEvents to establish interactive-session activity and perform a targeted post-logon tool hunt.
- Built a confidence matrix and separated incident-associated source indicators from confirmed malicious IOCs.

## SOC skills demonstrated

`Defender Advanced Hunting`, `RDP/NTLM investigation`, `Authentication correlation`, `Network-to-logon timeline reconstruction`, `Post-logon process hunting`, `Confidence and scope assessment`

## Report structure

The full PDF report contains the investigation findings, evidence-led summary, timeline where applicable, 5Ws and 1H, observed or incident-associated indicators, assessment, recommendations and documented investigation limitations.

---

**Prepared by Graham McKean**  
SOC investigation portfolio case study. External indicators are defanged where applicable.
