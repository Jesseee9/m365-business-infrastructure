# IT Operations & Incident Log: Guest Turnover Solutions

This log documents technical challenges and configuration hurdles encountered during the management of the GTS infrastructure.

---

## 🟢 Incident #004: Security Hardening License Constraint
**Date:** Feb 2, 2026  
**Category:** Security / Licensing  
**Status:** Resolved (Risk Accepted)

### Issue
During the weekly security audit, the Microsoft Secure Score (Defender Portal) recommended implementing "Impersonation Protection" and "Aggressive Phishing Thresholds" to increase the tenant score from 45.96%.

### Diagnosis
Investigated the "Anti-Phishing" policies within the Microsoft Defender for Office 365 portal. Confirmed that these specific hardening features (User/Domain Impersonation) are only available in **Defender for Office 365 Plan 1** or **M365 Business Premium** licenses. 

### Resolution
Current infrastructure is on **M365 Business Basic**. Verified that existing foundational security (SPF, DKIM, DMARC, and MFA Security Defaults) provides sufficient protection for the current risk profile.
**Lesson:** Infrastructure engineering requires balancing security recommendations against license costs. Posture remains optimal for the current subscription tier.

---

## 🟢 Incident #003: Power Automate Trigger Latency
**Date:** Jan 30, 2026  
**Category:** Automation / Power Platform  
**Status:** Resolved (Informational)

### Issue
Automated "Email to SharePoint" tracker did not immediately populate upon test receipt.

### Diagnosis
Researched M365 Business Basic polling intervals; identified that automated triggers have a latency of 3–5 minutes.

### Resolution
Performed Manual Test Trigger; confirmed connector health. 

---

