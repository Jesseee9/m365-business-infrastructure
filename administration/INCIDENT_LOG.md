# IT Operations & Incident Log: Guest Turnover Solutions

This log documents technical challenges, service interruptions, and configuration hurdles encountered during the management of the GTS infrastructure. Each entry follows the **Issue > Diagnosis > Resolution** framework.

---

## 🟢 Incident #003: Power Automate Trigger Latency
**Date:** Jan 30, 2026  
**Category:** Automation / Power Platform  
**Status:** Resolved (Informational)

### Issue
After deploying the "Email to SharePoint" enquiry tracker, test emails sent from external domains did not immediately populate the SharePoint list.

### Diagnosis
Checked the Power Automate **Run History**. Confirmed the flow status was 'On' but no runs were recorded. Researched M365 Business Basic polling intervals; identified that automated triggers can have a latency of 3–5 minutes depending on tenant load.

### Resolution
Performed a **Manual Test Trigger** within the Power Automate designer. Confirmed the connection between the Outlook V3 connector and SharePoint 'Create Item' action was 100% functional. 
**Lesson:** Polling latency is an expected behavior in lower-tier M365 licenses; manual verification is the standard for immediate deployment testing.

---

## 🟢 Incident #002: DKIM Cryptographic Validation Failure
**Date:** Jan 2026  
**Category:** Email Security / DNS  
**Status:** Resolved

### Issue
DKIM signatures were failing validation in the Microsoft 365 Defender portal despite CNAME records being added to Namecheap.

### Diagnosis
Used **MXToolbox** to perform a DNS lookup on the selectors. Identified that the CNAME string provided by Microsoft was being truncated by the DNS provider's UI during the initial paste.

### Resolution
Re-entered the full cryptographic strings manually, ensuring no hidden characters or truncations. Waited 30 minutes for DNS propagation. 
**Result:** DKIM status changed to "Enabled" and "Signing" in the Exchange Admin Center.

---

## 🟢 Incident #001: MX Record Priority Conflict
**Date:** Jan 2026  
**Category:** Mail Flow / DNS  
**Status:** Resolved

### Issue
Inbound emails were bouncing with a "User Not Found" error.

### Diagnosis
Identified that Namecheap’s default "Private Email" settings were still active, causing a conflict with the new Microsoft 365 MX records. Two sets of MX records were active simultaneously.

### Resolution
Navigated to **Mail Settings** in Namecheap. Switched the setting from "Automatic" to "Custom MX." Deleted the old registrar records and set the Microsoft 365 MX record to **Priority 0**.
**Result:** Verified mail flow via external Gmail test; 100% delivery success.

---

## 📊 Summary of Operational Health
*   **Total Incidents Logged:** 3
*   **Mean Time to Resolution (MTTR):** < 1 Hour
*   **Common Root Cause:** DNS Propagation / Provider UI limitations
