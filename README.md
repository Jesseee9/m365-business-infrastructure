Microsoft 365 Infrastructure & Operations: Guest Turnover Solutions
🚀 Project Overview
A live, production-grade Microsoft 365 environment for Guest Turnover Solutions, a professional cleaning service in Hull, UK. This project has evolved from initial deployment into a managed operational environment featuring automation and business intelligence.
🌐 Live Site: guestturnoversolutions.co.uk
👤 My Role
Position: IT Administrator (Remote)
Focus: Infrastructure Management, Security Hardening, and Process Automation.
🏗 Architecture Diagram
┌─────────────────────────────────────────────────────────┐
│              CUSTOM DOMAIN (DNS)                        │
│          guestturnoversolutions.co.uk                   │
└─────────────────────────────────────────────────────────┘
              │                           │
    ┌─────────┴─────────┐       ┌─────────┴─────────┐
    ▼                   ▼       ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│  GitHub Pages   │ │ Google Analytics│ │  Microsoft 365  │
├─────────────────┤ ├─────────────────┤ ├─────────────────┤
│ Business Site   │ │ Traffic Monitor │ │ Exchange Online │
│ (HTML/CSS)      │ │ (GA4 Metrics)   │ │ (Email Security)│
└─────────────────┘ └─────────────────┘ └────────┬────────┘
                                                 │
    ┌────────────────────────────────────────────┴────────┐
    ▼                                                     ▼
┌─────────────────┐ ┌─────────────────┐         ┌─────────────────┐
│    Entra ID     │ │ Power Automate  │ ──────▶ │    SharePoint   │
├─────────────────┤ ├─────────────────┤         ├─────────────────┤
│ • MFA Enabled   │ │ Enquiry Tracker │         │ Operations Site │
│ • Security Def. │ │ (Logic Flow)    │         │ • Lead Database │
│ • Break-glass   │ │                 │         │ • Checklists    │
└─────────────────┘ └─────────────────┘         └─────────────────┘
🛠 The Technical Stack
Category	Technology	Purpose
Automation	Power Automate	Automated Lead Tracking (Email -> SharePoint)
Analytics	Google Analytics (GA4)	Monitoring user traffic and digital ROI
Email Security	SPF, DKIM, DMARC	100% Authentication (MXToolbox Verified)
Identity	Microsoft Entra ID	MFA, Security Defaults, Break-glass
Web	GitHub Pages / DNS	Custom domain management via Namecheap
Collab	SharePoint Online	Centralized Operations & Contract Storage
🚀 Key Operational Achievements
1. Business Process Automation
To eliminate manual lead tracking, I designed a custom Enquiry Tracker:
Workflow: Logic flow monitors the business inbox and extracts 'Subject', 'From', and 'Timestamp'.
Storage: Automatically populates a SharePoint Operations List.
Result: Provides the business owner with a real-time database of customer requests, reducing manual entry by 100%.
2. Security Hardening
Identity: Enforced MFA for all accounts via Entra ID Security Defaults.
Resilience: Configured a Break-Glass emergency account on the .onmicrosoft.com domain to ensure access during DNS or domain failures.
Reputation: Configured SPF, DKIM, and DMARC (quarantine policy) to ensure professional email deliverability and prevent spoofing.
3. Data-Driven Monitoring
Integrated GA4 global site tags to monitor acquisition and engagement.
I use these metrics to provide monthly visibility on website performance to the business owner.
🛠 Troubleshooting & Incident Log
I maintain a professional INCIDENT_LOG.md for all technical challenges.
Recent Case: Automation Polling Interval (Jan 2026)
Issue: Automated flow did not trigger immediately upon receipt.
Diagnosis: Verified M365 Business Basic polling latency (approx. 5 mins).
Resolution: Performed manual polling test; confirmed connector health and production-readiness.
📊 Skills Demonstrated
Cloud Admin: M365, Exchange, SharePoint, Entra ID
Automation: Power Automate (Logic Flows)
Security: MFA, SPF/DKIM/DMARC, Identity Governance
Operations: Incident logging, DNS Management (MX, TXT, CNAME, A)
