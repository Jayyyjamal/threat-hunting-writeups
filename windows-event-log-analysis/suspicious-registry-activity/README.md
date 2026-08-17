
# 📝 Suspicious Registry Activity Detection

## Threat Hunting Writeup

### 🔎 Investigation Objective

The objective of this investigation was to identify and analyze potentially suspicious Windows Registry modifications that could indicate persistence, configuration changes, or defense-evasion activity.

---

# 🧪 Lab Environment

| Component | Technology |
|-----------|------------|
| SIEM | Wazuh |
| Endpoint | Windows 11 |
| Server | Ubuntu |
| Virtualization | Oracle VirtualBox |
| Telemetry | Windows Event Logs |

---

# 🔍 Investigation Approach

I monitored Windows endpoint telemetry for registry-related activity and investigated changes involving potentially security-sensitive registry locations.

The investigation focused on:

- Registry modifications
- Persistence-related locations
- Startup configuration
- Security-related settings
- Process activity surrounding registry changes

---

# 🧠 Investigation Hypothesis

Attackers may modify specific Windows Registry locations to establish persistence, change system configuration, or weaken security controls.

Therefore, unexpected registry modifications should be investigated alongside the process, user, timestamp, and surrounding events.

---

# 🔎 Analysis Workflow

```text
Registry Event
      ↓
Identify Modified Key
      ↓
Identify User
      ↓
Identify Process
      ↓
Review Timestamp
      ↓
Correlate Surrounding Events
      ↓
Determine Legitimate vs Suspicious
```

---

# 🗺️ MITRE ATT&CK Relevance

Potentially relevant techniques include:

- **T1112 – Modify Registry**
- **T1547 – Boot or Logon Autostart Execution**

---

# 🛡️ Recommended SOC Actions

For suspicious registry activity, I would:

- Identify the process responsible for the modification.
- Validate the user account involved.
- Check whether the change was authorized.
- Review process execution around the same timestamp.
- Search for persistence mechanisms.
- Investigate related network activity.
- Revert unauthorized changes where appropriate.

---

# 📌 Findings

This investigation demonstrated how registry telemetry can be used as a source of threat-hunting evidence and how registry changes should be correlated with process and user activity before determining whether an event is malicious.

---

# 💡 Lessons Learned

Registry modifications are not inherently malicious. Effective threat hunting requires contextual analysis and correlation rather than treating every registry change as an alert.
