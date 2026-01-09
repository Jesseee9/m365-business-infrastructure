

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
- Professional web presence
- Professional email with custom domain
- Secure email that doesn't land in spam
- Centralised document storage for checklists and contracts
- Simple, low-maintenance solution

---

## Solution Built

| Component | Technology | Purpose |
|-----------|------------|---------|
| Website | GitHub Pages | Professional business website |
| Email | Exchange Online | Professional email with custom domain |
| Email Security | SPF, DKIM, DMARC | Prevent spoofing, ensure deliverability |
| Identity | Microsoft Entra ID | User management with MFA |
| Documents | SharePoint Online | Centralised file storage |

---

## Architecture Diagram
┌─────────────────────────────────────────────────────────┐
│ CUSTOM DOMAIN (DNS) │
│ guestturnoversolutions.co.uk │
└─────────────────────────────────────────────────────────┘
│
┌───────────────┴───────────────┐
▼ ▼
┌─────────────────┐ ┌─────────────────┐
│ GitHub Pages │ │ Microsoft 365 │
├─────────────────┤ ├─────────────────┤
│ Business │ │ Exchange Online │
│ Website │ │ (Email) │
│ │ │ │
│ • Services │ │ SPF ✅ │
│ • Contact Info │ │ DKIM ✅ │
│ • Service Areas │ │ DMARC ✅ │
└─────────────────┘ └────────┬────────┘
│
┌────────────────────┴────────────────────┐
▼ ▼
┌─────────────────┐ ┌─────────────────┐
│ Entra ID │ │ SharePoint │
├─────────────────┤ ├─────────────────┤
│ • MFA Enabled │ │ Operations Site │
│ • Security │ │ • Checklists │
│ Defaults ON │ │ • Contracts │
│ • Break-glass │ │ • Templates │
│ Account │ │ │
└─────────────────┘ └─────────────────┘

---

## What I Configured

### 1. Custom Domain & DNS
- Purchased and connected custom domain to Microsoft 365
- Configured DNS records for email (MX, TXT, CNAME)
- Configured DNS records for website (A records, CNAME)
- Managed DNS across two providers (Namecheap → M365 & GitHub)

### 2. Professional Website
- Deployed responsive business website using GitHub Pages
- Connected custom domain with HTTPS
- Mobile-friendly design
- Contact information and service details

🌐 **Live site:** [guestturnoversolutions.co.uk](https://guestturnoversolutions.co.uk)

### 3. Email Security
| Record | Purpose | Status |
|--------|---------|--------|
| SPF | Prevents email spoofing | ✅ Configured |
| DKIM | Cryptographic email signing | ✅ Enabled |
| DMARC | Policy enforcement | ✅ Configured |

**Verification:** 29/29 tests passed on MXToolbox

### 4. Identity Management (Entra ID)
- Enabled Security Defaults (MFA for all users)
- Created break-glass emergency admin account
- Implemented professional naming conventions
- Configured password policies

### 5. SharePoint Document Structure
📁 Operations Site
├── 📁 Cleaning Checklists
├── 📁 Property Information
├── 📁 Client Contracts
├── 📁 Training Materials
└── 📁 Templates

---

## Challenges & Troubleshooting

Real issues encountered during deployment and how I resolved them:

### 1. DKIM CNAME Record Configuration
| Issue | Cause | Solution |
|-------|-------|----------|
| DKIM records not validating | CNAME values very long and complex | Carefully copied full values, verified in Microsoft Defender portal |

### 2. MX Record Setup in Namecheap
| Issue | Cause | Solution |
|-------|-------|----------|
| MX record not appearing | Namecheap has separate Mail Settings section | Located Mail Settings, selected Custom MX, added Microsoft's mail server |

### 3. DNS Propagation Delays
| Issue | Cause | Solution |
|-------|-------|----------|
| Domain verification not completing | DNS changes take time to propagate | Waited 15-30 minutes, used MXToolbox to verify before retrying |

### 4. GitHub Pages Custom Domain
| Issue | Cause | Solution |
|-------|-------|----------|
| Website not loading on custom domain | DNS records needed for GitHub | Added 4 A records and CNAME for www to Namecheap |

---

## Lessons Learned

1. **Always verify DNS changes** using external tools (MXToolbox) before assuming they failed
2. **Break-glass accounts** should use `.onmicrosoft.com` domain for DNS independence
3. **Email security is layered** - SPF, DKIM, and DMARC work together
4. **Keep solutions simple** - build what the business needs, not everything possible
5. **Document as you go** - screenshots save troubleshooting time

---

## Skills Demonstrated

| Category | Skills |
|----------|--------|
| **Identity & Access** | Entra ID, MFA, Security Defaults, Break-glass accounts |
| **Email** | Exchange Online, SPF, DKIM, DMARC |
| **Collaboration** | SharePoint Online, Document libraries |
| **Web Deployment** | GitHub Pages, Custom domains, HTTPS |
| **DNS Management** | MX, TXT, CNAME, A records across multiple providers |

---

## Screenshots

Evidence of configuration available in the `/screenshots` folder.

---

## Related Repositories

🌐 **Website Code:** [guest-turnover-website](https://github.com/jesseee9/guest-turnover-website)

---

