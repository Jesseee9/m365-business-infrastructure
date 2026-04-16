# Microsoft 365 Infrastructure & Operations: Guest Turnover Solutions

## 🚀 Project Overview
A live, production-grade Microsoft 365 environment for **Guest Turnover Solutions**, a professional cleaning service in Hull, UK. This project has evolved from initial deployment into a managed operational environment featuring **automation**, **security hardening**, and **business intelligence**.

**🌐 Live Site:** [guestturnoversolutions.co.uk](https://guestturnoversolutions.co.uk)

## 👤 My Role
**Position:** IT Support Technician (Volunteer)  
**Focus:** Infrastructure Management, Security Hardening, Process Automation, and Ongoing Operations.

## 🏗 Architecture Diagram
```text
┌─────────────────────────────────────────────────────────┐
│                    CUSTOM DOMAIN (DNS)                  │
│              guestturnoversolutions.co.uk                │
│                   Managed via Namecheap                  │
└─────────────────────────────────────────────────────────┘
              │                           │
    ┌─────────┴─────────┐       ┌─────────┴─────────┐
    ▼                   ▼       ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│  GitHub Pages   │ │ Google Analytics │ │  Microsoft 365  │
├─────────────────┤ ├─────────────────┤ ├─────────────────┤
│ Business Site   │ │ Traffic Monitor │ │ Exchange Online │
│ (HTML/CSS)      │ │ (GA4)           │ │ (Email + Auth)  │
│ Tawk.to Chat    │ │                 │ │ SPF/DKIM/DMARC  │
└─────────────────┘ └─────────────────┘ └────────┬────────┘
                                                 │
    ┌────────────────────────────────────────────┴────────┐
    ▼                                                     ▼
┌─────────────────┐ ┌─────────────────┐         ┌─────────────────┐
│    Entra ID     │ │ Power Automate  │ ──────▶ │    SharePoint   │
├─────────────────┤ ├─────────────────┤         ├─────────────────┤
│ • MFA Enabled   │ │ Enquiry Tracker │         │ Operations Site │
│ • Security Def. │ │ (Auto Lead Log) │         │ • Lead Database │
│ • Break-glass   │ │                 │         │ • Documents     │
│ • Secure Score  │ │                 │         │ • Checklists    │
└─────────────────┘ └─────────────────┘         └─────────────────┘🛠 The Technical Stack
Category	Technology	Purpose
Automation	Power Automate	Automated Lead Tracking (Email → SharePoint)
Analytics	Google Analytics (GA4)	Monitoring user traffic and digital ROI
Email Security	SPF, DKIM, DMARC	100% Authentication (MXToolbox Verified)
Identity	Microsoft Entra ID	MFA, Security Defaults, Break-glass Account, Secure Score
Web Hosting	GitHub Pages	Business website with custom domain and HTTPS
Live Chat	Tawk.to	Real-time customer chat widget integrated into the website
Domain	Namecheap	Domain registration and DNS management (A, MX, TXT, CNAME)
Collaboration	SharePoint Online	Centralised Operations, Lead Database, and Document Storage
🚀 Key Operational Achievements
1. Business Process Automation
To eliminate manual lead tracking, I designed a custom Enquiry Tracker:

Workflow: Logic flow monitors the business inbox and extracts Subject, From, and Timestamp.
Storage: Automatically populates a SharePoint Operations List.
Result: Provides the business owner with a real-time database of customer requests, reducing manual entry by 100%.
2. Security Hardening
Identity: Enforced MFA for all accounts via Entra ID Security Defaults.
Resilience: Configured a Break-Glass emergency account on the .onmicrosoft.com domain to ensure access during DNS or domain failures.
Reputation: Configured SPF, DKIM, and DMARC (quarantine policy) to ensure professional email deliverability and prevent spoofing.
Monitoring: Regular Secure Score reviews with ongoing implementation of recommended improvements.
3. Data-Driven Monitoring
Integrated GA4 global site tags to monitor acquisition and engagement.
I use these metrics to provide monthly visibility on website performance to the business owner.
4. Live Customer Communication
Integrated Tawk.to live chat widget into the business website.
Customers can start a conversation directly from the site without needing to send an email.
Enquiries received through chat are monitored and responded to through the Tawk.to dashboard.
5. Website Deployment
Built the business website using HTML and CSS.
Deployed and hosted on GitHub Pages with the custom domain and enforced HTTPS.
DNS configured through Namecheap with A records pointing to GitHub Pages and MX records pointing to Microsoft 365.
🛠 Troubleshooting & Incident Log
I maintain a professional incident log for all technical challenges.

Case 1: Automation Polling Interval (Jan 2026)
Issue: Automated flow did not trigger immediately upon receipt.
Diagnosis: Verified M365 Business Basic polling latency (approx. 5 mins).
Resolution: Performed manual polling test; confirmed connector health and production-readiness. Documented as a known platform limitation.
📊 Skills Demonstrated
Cloud Admin: M365, Exchange Online, SharePoint Online, Entra ID
Automation: Power Automate (Logic Flows)
Security: MFA, SPF/DKIM/DMARC, Identity Governance, Secure Score
Web: GitHub Pages, Custom Domain, SSL/HTTPS, Tawk.to Live Chat
Analytics: Google Analytics (GA4)
Operations: Incident Logging, DNS Management (MX, TXT, CNAME, A), Domain Management (Namecheap)
