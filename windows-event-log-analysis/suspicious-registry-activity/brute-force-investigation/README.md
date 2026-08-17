
# 🔐 Brute Force Attack Investigation

## Threat Hunting Writeup

### 🔎 Investigation Objective

The objective of this investigation was to identify authentication patterns that could indicate a brute-force attack against a Windows endpoint.

---

# 🧪 Lab Environment

| Component | Technology |
|-----------|------------|
| SIEM | Wazuh |
| Endpoint | Windows 11 |
| Server | Ubuntu |
| Virtualization | Oracle VirtualBox |
| Log Source | Windows Security Logs |

---

# 🚨 Detection Scenario

A high volume of failed authentication attempts against an account may indicate:

- Password guessing
- Brute-force activity
- Credential stuffing
- Unauthorized access attempts

The investigation focused on identifying repeated authentication failures and determining whether the behavior was consistent with normal user activity.

---

# 🔍 Investigation Workflow

```text
Authentication Logs
        ↓
Identify Failed Attempts
        ↓
Group by Source
        ↓
Identify Target Account
        ↓
Analyze Frequency
        ↓
Build Timeline
        ↓
Investigate Successful Login
        ↓
Determine Threat Level
```

---

# 📊 Investigation Areas

I analyzed:

- Source IP address
- Target username
- Authentication timestamps
- Number of failed attempts
- Successful authentication following failures
- Host involved
- Authentication pattern

---

# 🧠 Investigation Hypothesis

An attacker attempting to gain unauthorized access may generate repeated authentication failures against one or more accounts.

A successful authentication following a high volume of failures would increase the priority of the investigation.

---

# 🗺️ MITRE ATT&CK Relevance

Potentially relevant techniques include:

- **T1110 – Brute Force**
- **T1110.001 – Password Guessing**
- **T1110.003 – Password Spraying**

---

# 🛡️ Recommended SOC Actions

If brute-force activity were confirmed, I would:

1. Identify the source IP.
2. Determine whether the source is trusted.
3. Identify targeted accounts.
4. Review successful authentication events.
5. Check for lateral movement.
6. Temporarily block or restrict malicious sources where appropriate.
7. Reset compromised credentials.
8. Continue monitoring for additional attempts.

---

# 📌 Findings

The investigation demonstrated how authentication logs can be used to identify abnormal login patterns and establish whether repeated failures represent potential brute-force activity.

---

# 💡 Lessons Learned

Brute-force detection becomes more effective when analysts correlate authentication failures with source IP, target account, timing, and subsequent successful logins instead of relying solely on the number of failed attempts.
