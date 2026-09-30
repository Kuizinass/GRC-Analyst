# Risk Register: Northwind Health

> Scored using the [methodology](../docs/02-methodology.md): Likelihood × Impact (1–25). Also available as a [CSV](risk-register.csv) for filtering and sorting.

## Summary

| ID | Risk | L | I | Score | Rating | Treatment | Owner | Residual |
|---|---|---|---|---|---|---|---|---|
| R-01 | Phishing leading to credential theft and account takeover | 4 | 5 | **20** | 🔴 Critical | Mitigate | IT Manager | 8 🟡 |
| R-02 | Unauthorized or excessive internal access to patient records | 3 | 5 | **15** | 🟠 High | Mitigate | CTO | 8 🟡 |
| R-03 | Cloud misconfiguration exposing patient documents publicly | 3 | 5 | **15** | 🟠 High | Mitigate | CTO | 8 🟡 |
| R-05 | Ransomware or destructive attack causing extended outage | 3 | 5 | **15** | 🟠 High | Mitigate | CTO | 6 🟡 |
| R-04 | Vendor breach or misuse of patient data | 3 | 4 | **12** | 🟠 High | Mitigate | Compliance Manager | 6 🟡 |
| R-06 | Malicious activity goes undetected | 4 | 3 | **12** | 🟠 High | Mitigate | CTO | 6 🟡 |
| R-09 | Former employees retain access to systems with ePHI | 3 | 4 | **12** | 🟠 High | Mitigate | IT Manager | 4 🟢 |
| R-08 | Exploitation of vulnerable third-party libraries | 3 | 3 | **9** | 🟡 Medium | Mitigate | CTO | 4 🟢 |
| R-07 | Lost or stolen device exposing exported patient data | 2 | 4 | **8** | 🟡 Medium | Mitigate | IT Manager | 3 🟢 |
| R-10 | Slow or disorganized response to a breach, missing notification deadlines | 2 | 4 | **8** | 🟡 Medium | Mitigate | Compliance Manager | 4 🟢 |
| R-11 | Unauthorized physical access | 1 | 3 | **3** | 🟢 Low | Accept | CTO | 3 🟢 |

## Risk Details

### R-01 · Phishing leading to credential theft and account takeover

| | |
|---|---|
| **Asset** | Workforce email & SSO accounts |
| **Vulnerability** | MFA not enforced for all users; some accounts use SMS codes |
| **Existing controls** | Security awareness video at onboarding; email filtering |
| **Inherent risk** | Likelihood 4 × Impact 5 = **20** (🔴 Critical) |
| **Treatment** | Mitigate: Enforce phishing-resistant MFA (security keys or passkeys) for all staff; block legacy authentication |
| **Owner / target** | IT Manager · 30 days |
| **Residual risk** | Likelihood 2 × Impact 4 = **8** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: PR.AA · HIPAA: §164.312(d) · SOC 2: CC6.1 |

### R-02 · Unauthorized or excessive internal access to patient records

| | |
|---|---|
| **Asset** | Patient database (ePHI) |
| **Vulnerability** | 12 engineers have standing production access; no periodic access reviews |
| **Existing controls** | SSO login; database audit logging enabled |
| **Inherent risk** | Likelihood 3 × Impact 5 = **15** (🟠 High) |
| **Treatment** | Mitigate: Move to just-in-time access with approval; quarterly access reviews signed off by data owner |
| **Owner / target** | CTO · 90 days |
| **Residual risk** | Likelihood 2 × Impact 4 = **8** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: PR.AA · HIPAA: §164.312(a)(1); §164.308(a)(4) · SOC 2: CC6.2; CC6.3 |

### R-03 · Cloud misconfiguration exposing patient documents publicly

| | |
|---|---|
| **Asset** | S3 document storage (ePHI) |
| **Vulnerability** | No automated configuration scanning; changes made manually in console |
| **Existing controls** | Block Public Access enabled at account level; encryption at rest |
| **Inherent risk** | Likelihood 3 × Impact 5 = **15** (🟠 High) |
| **Treatment** | Mitigate: Deploy automated cloud configuration monitoring; manage storage settings as code with review |
| **Owner / target** | CTO · 90 days |
| **Residual risk** | Likelihood 2 × Impact 4 = **8** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: PR.PS; DE.CM · HIPAA: §164.312(a)(1) · SOC 2: CC6.1; CC7.1 |

### R-04 · Vendor breach or misuse of patient data

| | |
|---|---|
| **Asset** | ePHI shared with SMS reminder vendor |
| **Vulnerability** | No Business Associate Agreement (BAA) signed; no vendor security review |
| **Existing controls** | Vendor uses TLS in transit |
| **Inherent risk** | Likelihood 3 × Impact 4 = **12** (🟠 High) |
| **Treatment** | Mitigate: Sign BAA or replace vendor; complete vendor security questionnaire before renewal |
| **Owner / target** | Compliance Manager · 30 days |
| **Residual risk** | Likelihood 2 × Impact 3 = **6** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: GV.SC · HIPAA: §164.308(b)(1) · SOC 2: CC9.2 |

### R-05 · Ransomware or destructive attack causing extended outage

| | |
|---|---|
| **Asset** | Production platform & backups |
| **Vulnerability** | Backup restores never tested; backups in same AWS account |
| **Existing controls** | Daily automated database snapshots |
| **Inherent risk** | Likelihood 3 × Impact 5 = **15** (🟠 High) |
| **Treatment** | Mitigate: Test restores quarterly; copy backups to an isolated account with immutable retention |
| **Owner / target** | CTO · 90 days |
| **Residual risk** | Likelihood 2 × Impact 3 = **6** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: PR.IR; RC.RP · HIPAA: §164.308(a)(7) · SOC 2: A1.2; A1.3 |

### R-06 · Malicious activity goes undetected

| | |
|---|---|
| **Asset** | Production environment |
| **Vulnerability** | Logs collected but no alerting or regular review; no owner for monitoring |
| **Existing controls** | CloudTrail enabled; application logs retained 30 days |
| **Inherent risk** | Likelihood 4 × Impact 3 = **12** (🟠 High) |
| **Treatment** | Mitigate: Define high-priority alerts (e.g. bulk ePHI export, privilege changes); assign weekly review owner; extend retention to 1 year |
| **Owner / target** | CTO · 90 days |
| **Residual risk** | Likelihood 2 × Impact 3 = **6** (🟡 Medium) |
| **Mapping** | NIST CSF 2.0: DE.CM · HIPAA: §164.312(b); §164.308(a)(1)(ii)(D) · SOC 2: CC7.2 |

### R-07 · Lost or stolen device exposing exported patient data

| | |
|---|---|
| **Asset** | Employee laptops |
| **Vulnerability** | Full-disk encryption not enforced on ~15% of laptops; staff export CSVs for support tasks |
| **Existing controls** | Device management tool on most laptops |
| **Inherent risk** | Likelihood 2 × Impact 4 = **8** (🟡 Medium) |
| **Treatment** | Mitigate: Enforce full-disk encryption via device management; replace CSV exports with in-app reporting |
| **Owner / target** | IT Manager · 6 months |
| **Residual risk** | Likelihood 1 × Impact 3 = **3** (🟢 Low) |
| **Mapping** | NIST CSF 2.0: PR.DS · HIPAA: §164.310(d)(1); §164.312(a)(2)(iv) · SOC 2: CC6.7 |

### R-08 · Exploitation of vulnerable third-party libraries

| | |
|---|---|
| **Asset** | Scheduling application |
| **Vulnerability** | No automated dependency scanning; patching done ad hoc |
| **Existing controls** | Annual external penetration test |
| **Inherent risk** | Likelihood 3 × Impact 3 = **9** (🟡 Medium) |
| **Treatment** | Mitigate: Add dependency scanning to the build pipeline; define patching timelines by severity |
| **Owner / target** | CTO · 6 months |
| **Residual risk** | Likelihood 2 × Impact 2 = **4** (🟢 Low) |
| **Mapping** | NIST CSF 2.0: ID.RA; PR.PS · HIPAA: §164.308(a)(1)(ii)(B) · SOC 2: CC7.1; CC8.1 |

### R-09 · Former employees retain access to systems with ePHI

| | |
|---|---|
| **Asset** | Workforce accounts |
| **Vulnerability** | Offboarding is manual and relies on HR emailing IT; no deprovisioning checklist |
| **Existing controls** | Most leavers disabled within a week |
| **Inherent risk** | Likelihood 3 × Impact 4 = **12** (🟠 High) |
| **Treatment** | Mitigate: Automate deprovisioning from HR system; same-day access removal target; monthly leaver audit |
| **Owner / target** | IT Manager · 90 days |
| **Residual risk** | Likelihood 1 × Impact 4 = **4** (🟢 Low) |
| **Mapping** | NIST CSF 2.0: PR.AA · HIPAA: §164.308(a)(3)(ii)(C) · SOC 2: CC6.2 |

### R-10 · Slow or disorganized response to a breach, missing notification deadlines

| | |
|---|---|
| **Asset** | Incident response capability |
| **Vulnerability** | Incident response plan exists but has never been tested; roles unclear |
| **Existing controls** | Documented IR plan (2024) |
| **Inherent risk** | Likelihood 2 × Impact 4 = **8** (🟡 Medium) |
| **Treatment** | Mitigate: Update IR plan with HIPAA breach notification steps; run an annual tabletop exercise |
| **Owner / target** | Compliance Manager · 6 months |
| **Residual risk** | Likelihood 1 × Impact 4 = **4** (🟢 Low) |
| **Mapping** | NIST CSF 2.0: RS.MA · HIPAA: §164.308(a)(6) · SOC 2: CC7.3; CC7.4 |

### R-11 · Unauthorized physical access

| | |
|---|---|
| **Asset** | Austin office |
| **Vulnerability** | Shared office with badge access; no ePHI stored on premises |
| **Existing controls** | Building badge access; remote-first workforce |
| **Inherent risk** | Likelihood 1 × Impact 3 = **3** (🟢 Low) |
| **Treatment** | Accept: Accept: no ePHI or production systems on premises. Review annually |
| **Owner / target** | CTO · Annual review |
| **Residual risk** | Likelihood 1 × Impact 3 = **3** (🟢 Low) |
| **Mapping** | NIST CSF 2.0: PR.AA · HIPAA: §164.310(a)(1) · SOC 2: CC6.4 |
