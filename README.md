# m365-business-infrastructure
Microsoft 365 infrastructure build for a small business


# Microsoft 365 Small Business Infrastructure

## Project Overview

Complete Microsoft 365 infrastructure deployment for **Guest Turnover Solutions**, a professional cleaning service for Airbnb hosts and holiday let landlords based in Hull, UK.

---

## My Role

**Position:** IT Administrator  
**Type:** Remote Infrastructure Management  
**Scope:** Full deployment and configuration of cloud-based business systems

---

## Business Problem

The business needed:
- Professional email presence
- A way for clients to book cleaning services online
- Secure document storage for checklists and contracts
- Automated notifications when bookings are made

---

## Solution Built

| Component | Technology | Purpose |
|-----------|------------|---------|
| Identity | Microsoft Entra ID | User management with MFA |
| Email | Exchange Online | Professional email with custom domain |
| Documents | SharePoint Online | Centralised file storage |
| Bookings | Microsoft Bookings | Client self-service scheduling |
| Automation | Power Automate | Booking notification emails |

---

## Architecture Diagram
┌─────────────────────────────────────────────────────────┐
│ ENTRA ID (Identity) │
│ MFA Enabled | Security Defaults ON │
└─────────────────────────────────────────────────────────┘
│
┌───────────────────┼───────────────────┐
▼ ▼ ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ Exchange │ │ SharePoint │ │ Bookings │
│ Online │ │ Online │ │ │
├──────────────┤ ├──────────────┤ ├──────────────┤
│ SPF ✅ │ │ Team Site │ │ Services │
│ DKIM ✅ │ │ Document │ │ Configured │
│ DMARC ✅ │ │ Library │ │ │
└──────────────┘ └──────────────┘ └──────────────┘
│
▼
┌──────────────────────┐
│ Power Automate │
│ Booking Alerts │
└──────────────────────┘

---

## What I Configured

### 1. Custom Domain & DNS
- Purchased and connected custom domain to Microsoft 365
- Configured DNS records: MX, TXT, CNAME
- Verified domain ownership

### 2. Email Security
| Record | Purpose | Status |
|--------|---------|--------|
| SPF | Prevents email spoofing | ✅ Configured |
| DKIM | Cryptographic email signing | ✅ Enabled |
| DMARC | Policy enforcement | ✅ Configured |

**Verification:** 29/29 tests passed on MXToolbox

### 3. Identity Management (Entra ID)
- Enabled Security Defaults (MFA for all users)
- Created break-glass emergency admin account
- Implemented professional naming conventions

### 4. SharePoint Document Structure
📁 Operations Site
├── 📁 Cleaning Checklists
├── 📁 Property Information
├── 📁 Client Contracts
├── 📁 Training Materials
└── 📁 Templates

### 5. Microsoft Bookings
- Created booking calendar for cleaning services
- Defined service types and durations
- Configured business hours

### 6. Power Automate
- Built automated flow: New Booking → Email Notification
- Integrated Bookings with Exchange Online

---
---

## Challenges & Troubleshooting

Real issues encountered during deployment and how I resolved them:

### 1. DKIM CNAME Record Configuration
| Issue | Cause | Solution |
|-------|-------|----------|
| DKIM records not validating | CNAME values from Microsoft were very long and complex | Carefully copied full CNAME values including `.onmicrosoft.com` suffix, verified in Microsoft Defender portal |

### 2. MX Record Setup in Namecheap
| Issue | Cause | Solution |
|-------|-------|----------|
| MX record not appearing in DNS settings | Namecheap handles MX records in a separate "Mail Settings" section | Located Mail Settings, selected "Custom MX", added Microsoft's mail server with priority 0 |

### 3. Microsoft Bookings - Blank Page Error
| Issue | Cause | Solution |
|-------|-------|----------|
| Public booking page showed blank with "error occurred" | Staff members not assigned to services | Identified need to assign staff to each service before page functions (documented for future fix) |

### 4. Power Automate - Connection Errors
| Issue | Cause | Solution |
|-------|-------|----------|
| "Invalid connection" and "Booking page is required" errors | Trigger not fully configured; Bookings connector needed authentication | Re-authenticated connection with business account, selected correct Booking calendar in trigger settings |

### 5. DNS Propagation Delays
| Issue | Cause | Solution |
|-------|-------|----------|
| Domain verification not completing immediately | DNS changes take time to propagate globally | Waited 15-30 minutes, used MXToolbox to verify propagation before retrying verification |

---

## Lessons Learned

1. **Always verify DNS changes** using external tools (MXToolbox) before assuming they failed
2. **Break-glass accounts** should use the `.onmicrosoft.com` domain for DNS independence
3. **Email security is layered** - SPF, DKIM, and DMARC work together
4. **Read error messages carefully** - they usually point to the exact fix needed
5. **Document as you go** - screenshots saved troubleshooting time when revisiting issues

---



## Skills Demonstrated

| Category | Skills |
|----------|--------|
| **Identity & Access** | Entra ID, MFA, Security Defaults, Break-glass accounts |
| **Email** | Exchange Online, SPF, DKIM, DMARC |
| **Collaboration** | SharePoint Online, Document libraries |
| **Business Apps** | Microsoft Bookings |
| **Automation** | Power Automate cloud flows |
| **DNS** | MX, TXT, CNAME record management |

---

## Screenshots

Evidence of configuration available in the `/screenshots` folder.

---
