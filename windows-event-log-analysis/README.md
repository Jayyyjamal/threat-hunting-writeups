
# 🪟 Windows Event Log Analysis

## Threat Hunting Writeup

### 🔎 Investigation Objective

The objective of this investigation was to analyze Windows Security Event Logs and identify account-related activity that could indicate suspicious behavior, privilege manipulation, or unauthorized access.

---

## 🧪 Lab Environment

| Component | Technology |
|-----------|------------|
| SIEM | Wazuh |
| Endpoint | Windows 11 |
| Server | Ubuntu |
| Virtualization | Oracle VirtualBox |
| Log Source | Windows Security Event Logs |

---

# 🚨 Events Investigated

| Event ID | Description |
|----------|-------------|
| 4720 | User account was created |
| 4726 | User account was deleted |
| 4732 | User was added to a security-enabled local group |
| 4733 | User was removed from a security-enabled local group |

These events were investigated because attackers may abuse legitimate account-management functionality to establish persistence, escalate privileges, or manipulate access.

---

# 🔍 Investigation Process

### 1. Log Collection

Windows Security Event Logs were collected through the Wazuh agent and forwarded to the Wazuh Manager.

### 2. Event Filtering

I used Wazuh Discover to isolate specific Windows Security Event IDs.

Example queries:

```text
data.win.system.eventID:4720
```

```text
data.win.system.eventID:4726
```

```text
data.win.system.eventID:4732
```

```text
data.win.system.eventID:4733
```

### 3. Event Analysis

For each event, I examined:

- Timestamp
- Host
- Username
- Target account
- Security group
- Subject account
- Account identifiers
- Event sequence

### 4. Correlation

I correlated related account-management events to determine whether the activity represented normal administrative behavior or potentially suspicious activity.

---

# 🧠 Investigation Hypothesis

An attacker with access to a Windows endpoint may attempt to create an account or modify security group membership to maintain access or obtain elevated privileges.

Therefore, account creation followed by group membership modification would require additional investigation.

---

# 🗺️ MITRE ATT&CK Relevance

Potentially relevant techniques include:

- **T1136 – Create Account**
- **T1098 – Account Manipulation**
- **T1068 – Exploitation for Privilege Escalation**

---

# 📌 Findings

The investigation successfully demonstrated the ability to:

- Detect Windows account creation
- Detect account deletion
- Detect local security group modifications
- Filter Windows Security Events using Wazuh
- Correlate related account activity
- Investigate potential privilege-related behavior

---

# 🛡️ Recommended SOC Actions

If similar activity were detected on a production endpoint, I would:

1. Validate whether the action was authorized.
2. Identify the administrator or process responsible.
3. Review surrounding authentication events.
4. Check for additional account modifications.
5. Investigate suspicious processes associated with the activity.
6. Escalate the incident if unauthorized activity is confirmed.

---

# 💡 Lessons Learned

This investigation reinforced the importance of monitoring account-management events because seemingly legitimate administrative actions can also be abused by attackers.
