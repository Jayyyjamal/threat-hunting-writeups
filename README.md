# 🧪 Threat Hunting & Security Writeups

## SOC Analyst Portfolio

This repository contains hands-on threat hunting investigations performed in a controlled lab environment using security monitoring and analysis tools.

The objective of these investigations is to develop practical SOC Analyst skills by analyzing security telemetry, identifying suspicious activity, developing investigation hypotheses, and documenting findings.

---

## 🎯 Objectives

Through these investigations, I focused on:

- 🔍 Threat hunting and security event analysis
- 🧠 Developing investigation hypotheses
- 📊 Log analysis and event correlation
- 🚨 Identifying suspicious behavior
- 🕵️ Investigating potential attack patterns
- 🛡️ Mapping findings to security controls and MITRE ATT&CK
- 📝 Documenting investigation findings and recommendations

---

# 🧪 Threat Hunting Investigations

## 1. 🪟 Windows Event Log Analysis

Investigated Windows Security Event Logs to identify account-related activity and determine whether the observed behavior could indicate unauthorized access or privilege manipulation.

**Focus Areas:**

- Windows Security Events
- User account activity
- Account creation and deletion
- Security group modifications
- Event correlation
- Suspicious behavior identification

👉 [View Investigation](windows-event-log-analysis/)

---

## 2. 📝 Suspicious Registry Activity Detection

Investigated Windows Registry activity to identify potentially suspicious modifications that could be associated with persistence, configuration changes, or defense evasion.

**Focus Areas:**

- Windows Registry monitoring
- Suspicious registry modifications
- Persistence indicators
- Event correlation
- Threat hunting
- MITRE ATT&CK mapping

👉 [View Investigation](/suspicious-registry-activity)

---

## 3. 🔐 Brute Force Attack Investigation

Investigated authentication activity to identify patterns consistent with brute-force or repeated failed login attempts.

**Focus Areas:**

- Failed authentication attempts
- Login pattern analysis
- Source IP investigation
- Account targeting
- Event correlation
- Attack timeline development

👉 [View Investigation](windows-event-log-analysis/suspicious-registry-activity/brute-force-investigation/README.md)

---

# 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Wazuh | SIEM and security monitoring |
| Windows Event Logs | Endpoint telemetry |
| Windows Security Logs | Authentication and account activity |
| VirtualBox | Isolated lab environment |
| Ubuntu | Security monitoring infrastructure |
| Windows 11 | Monitored endpoint |

---

# 🔎 Investigation Methodology

For each investigation, I followed a structured SOC workflow:

```text
Telemetry Collection
        ↓
Initial Detection
        ↓
Hypothesis Development
        ↓
Event Filtering
        ↓
Log Correlation
        ↓
Timeline Analysis
        ↓
Threat Assessment
        ↓
MITRE ATT&CK Mapping
        ↓
Recommendations
```

---

# 📋 Investigation Framework

Each writeup follows a consistent structure:

1. **Investigation Objective**
2. **Environment**
3. **Detection / Trigger**
4. **Initial Hypothesis**
5. **Evidence Collection**
6. **Event Analysis**
7. **Timeline**
8. **MITRE ATT&CK Mapping**
9. **Findings**
10. **Recommended Actions**
11. **Lessons Learned**

---

# 🧠 SOC Analyst Skills Demonstrated

- 🔍 Threat Hunting
- 📊 Log Analysis
- 🚨 Alert Investigation
- 🧩 Event Correlation
- 🕐 Timeline Analysis
- 🪟 Windows Security Monitoring
- 🔐 Authentication Analysis
- 🛡️ Endpoint Security
- 🗺️ MITRE ATT&CK Mapping
- 📝 Security Documentation

---

# ⚠️ Disclaimer

All investigations in this repository were performed in a controlled lab environment for educational and defensive security purposes.

No unauthorized systems or real-world targets were involved.


