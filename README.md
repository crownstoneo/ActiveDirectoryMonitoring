# Monitoring Active Directory Security Events with Splunk

## Objective
Centralize and analyze Active Directory authentication and account activity to detect suspicious behavior.

---

## Environment

- Windows Server (Domain Controller)
- Windows Client Machines
- Splunk Server
- VirtualBox Lab Network

---

## Tools Used

- Active Directory
- Splunk
- Windows Event Logs
- Sysmon

---

## Methodology

1. Configured a Windows Server as the **Domain Controller**.
2. Joined Windows client machines to the domain.
3. Enabled **advanced auditing** for authentication and account events.
4. Forwarded **Windows Security Logs** to Splunk.
5. Generated test activities including:
   - Failed logins
   - Password changes
   - Privilege modifications
6. Created Splunk searches to identify:
   - Brute force login attempts
   - Account lockouts
   - Administrative privilege changes
7. Built dashboards to visualize authentication activity.

---

## Evidence

### Active Directory Identity and Group Structure

<img width="747" height="531" alt="Screenshot 2025-12-26 110002" src="https://github.com/user-attachments/assets/70d7773f-b162-4009-9840-da1c666fb833" />


Active Directory groups were created to enforce **role-based access control (RBAC)** across departments.

---

### Access Control Enforcement

<img width="823" height="472" alt="Screenshot 2025-12-26 130958" src="https://github.com/user-attachments/assets/77c388c0-1f5f-4cae-8253-78f1cddcfa80" />



A user attempting to access the **Sales department share** without proper permissions was denied, demonstrating correct **least-privilege access configuration**.

---

### Authentication Events in Splunk

<img width="708" height="516" alt="Screenshot 2025-12-19 230010" src="https://github.com/user-attachments/assets/dcde3c62-0bcd-4743-b6c1-bc5cbe439d98" />


Windows authentication events (Event ID 4624) were successfully ingested into Splunk, enabling centralized monitoring and analysis.

---

## Findings

Centralized log monitoring allows security teams to quickly detect:

- Unauthorized login attempts
- Privilege escalation attempts
- Suspicious authentication patterns

---

## Remediation / Best Practices

- Enable auditing for authentication events
- Centralize logs within a SIEM platform
- Alert on abnormal login behavior
- Apply least privilege access policies

---

## Lessons Learned

Monitoring identity-related logs is critical for detecting attacks such as:

- Brute force login attempts
- Credential abuse
- Privilege escalation
