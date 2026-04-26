# GTS Ops Hub — Personal IT Management Application

A personal internal web application built to manage, document, and support 
the IT operations of **Guest Turnover Solutions (GTS)** — a real small 
cleaning business where I volunteer as IT Technician.

Built entirely using AI-assisted development tools as part of my ongoing 
IT skill development journey.

---

## Why I Built This

Managing a real Microsoft 365 environment means daily, weekly, and monthly 
tasks that need structure. I originally tracked everything manually and 
across separate tools. This app centralises everything into one clean, 
dark-themed interface I can open and use every day.

It also serves as a live portfolio piece — every section of this app 
reflects real work I do on a real IT environment.

---

## What It Does

The app has 7 tabs accessible via a sidebar navigation:

### 1. Daily Checks
Step-by-step interactive checklist for all 6 daily IT checks:
- Email monitoring via outlook.office.com
- Website verification at guestturnoversolutions.co.uk 
  (SSL, layout, Tawk.to widget)
- Live chat monitoring via dashboard.tawk.to
- Microsoft 365 Service Health alerts via admin.microsoft.com
- Entra ID sign-in log glance via entra.microsoft.com
- Google Analytics traffic check via analytics.google.com

### 2. Weekly Checks
Full guided walkthrough for the 10 weekly health check tasks:
- Entra ID Sign-In Logs full review (last 7 days)
- Entra ID Secure Score review and recommendations
- Exchange Online Message Trace
- Exchange Quarantine Check
- Exchange Mail Flow Rules verification and testing
- SharePoint Document Libraries review and permissions check
- Power Automate Flow Run History review
- Full website check (browser, GitHub Pages, Google Analytics)
- Tawk.to weekly enquiry review
- Excel log completion (GTS Weekly Log v2)

### 3. Monthly Tasks
Four rotating monthly maintenance tasks — one per week:
- **Week 1** — Secure Score Improvement (security.microsoft.com)
- **Week 2** — Email Authentication Audit 
  (SPF, DKIM, DMARC via Namecheap and M365)
- **Week 3** — User Access Review 
  (Entra ID users, groups, break-glass account)
- **Week 4** — Power Automate Improvement 
  (flow review, new automation ideas)

### 4. Incident Desk
A structured 5-step incident logging interface:
1. Record incident basics (date, time, symptoms, who is affected)
2. Check Microsoft Service Health to determine if it is a platform issue
3. Investigate using relevant logs 
   (Entra ID, Exchange, Power Automate, GitHub, Tawk.to)
4. Attempt fix and test resolution
5. Log everything including root cause, steps taken, and time to resolution

All incidents are saved to **local storage** so they persist between 
sessions without needing a database or external service.

### 5. Architecture
7 expandable accordion cards documenting how the entire GTS IT environment 
was built:
- **Domain and DNS** — Namecheap, A records, MX records, 
  TXT records (SPF, DKIM, DMARC)
- **Microsoft 365 Tenant** — Business Basic setup, custom domain 
  connection, DNS verification
- **Entra ID** — User accounts, role assignments, MFA via Security 
  Defaults, break-glass account
- **Exchange Online** — Mailboxes, email alias, mailbox forwarding, 
  mail flow rules, SPF/DKIM/DMARC (29/29 on MXToolbox)
- **Website and GitHub Pages** — HTML/CSS site, custom domain, HTTPS, 
  Tawk.to integration, Google Analytics GA4
- **SharePoint Online** — Team site, 5 document libraries, role-based 
  permissions, Customer Enquiries list
- **Power Automate** — Enquiry tracking flow (Exchange → SharePoint), 
  weekly manual email flow, polling delay documentation

Each card includes:
- What I did
- Why I did it
- How I did it (full step-by-step)
- Interview answer (ready to use in job interviews)

### 6. GTS Quiz
Interactive multiple choice quiz covering:
- All daily, weekly, and monthly check procedures
- The 5-step incident procedure
- DNS record types (A, MX, TXT, CNAME)
- SPF, DKIM, and DMARC explanations
- Break-glass account purpose and configuration
- Power Automate polling delay and why it happens
- Tawk.to vs email enquiry separation
- SharePoint library structure and Customer Enquiries list columns
- MXToolbox result (29/29 passing tests)
- Security Defaults and what they enforce
- All 7 architecture sections and their interview answers

One question at a time. Score tracked throughout. Wrong answers reviewed 
at the end with correct explanations.

### 7. AI Assistant
An inbuilt AI chat interface powered by the **Google Gemini API**.

The assistant is loaded with full context about the GTS IT environment 
and can answer questions about:
- Daily, weekly, and monthly procedures
- Microsoft 365 administration
- Entra ID, Exchange Online, SharePoint, Power Automate
- DNS, email authentication (SPF, DKIM, DMARC)
- GitHub Pages, Namecheap, Tawk.to, Google Analytics
- IT support concepts and incident handling
- Architecture decisions and interview answers

---

## Technologies Used

| Technology | Purpose |
|---|---|
| React (via Vite) | Frontend framework |
| Vanilla CSS | Styling and dark theme |
| Google Gemini API | AI Assistant (gemini-2.5-flash-lite) |
| @google/generative-ai | Gemini SDK for JavaScript |
| lucide-react | Icons |
| Local Storage | Incident data persistence |

---

## Built With

- **Google Antigravity IDE** — AI-first development platform 
  (agent-assisted build)
- **Google AI Studio** — API key management and model testing

---

## IT Environment Covered

| Tool | Purpose |
|---|---|
| Microsoft 365 Business Basic | Core platform |
| Entra ID (Azure AD) | Identity, MFA, Secure Score |
| Exchange Online | Email, mail flow, authentication |
| SharePoint Online | Document management, enquiry logging |
| Power Automate | Workflow automation |
| Namecheap | Domain registration and DNS |
| GitHub Pages | Website hosting |
| Tawk.to | Live chat |
| Google Analytics GA4 | Website traffic monitoring |
| Microsoft Defender / security.microsoft.com | Security policies and Secure Score |

---

## Issues Encountered and Troubleshooting

A log of every real issue hit during the build and what was learned 
from each one.

### Issue 1 — API Key Exposed
**What happened:** The Gemini API key was shared in a chat during 
the build process.

**Impact:** The free tier quota for the entire Google Cloud project 
was drained immediately because the key was visible and active.

**Fix:** Deleted the exposed key in Google AI Studio and generated 
a fresh one. Only pasted the new key directly into Antigravity — 
never shared it anywhere else.

**Lesson learned:** API keys are tied to your Google Cloud project, 
not just to you personally. Sharing a key publicly — even briefly — 
can drain the entire project quota. Always keep keys private and 
only paste them into the tool that needs them.

---

### Issue 2 — Wrong Gemini Model Name (404 Error)
**What happened:** The agent used the model name 
`gemini-1.5-flash` which returned a 404 error: models/gemini-1.5-flash is not found for API version v1beta
**Why it happened:** Antigravity suggested an outdated model name. 
Gemini model names change frequently as Google deprecates old versions 
and releases new ones.

**Fix:** Updated the model name in `AIAssistant.jsx` to 
`gemini-2.0-flash`.

**Lesson learned:** Always verify current Gemini model names against 
the official Google AI documentation before using them in code. 
Model names that worked 6 months ago may already be deprecated.

---

### Issue 3 — Quota Exceeded (429 Error)
**What happened:** After fixing the model name, the AI Assistant 
returned a 429 quota exceeded error: Quota exceeded for metric: generate_content_free_tier_requests
limit: 0, model: gemini-2.0-flash
Quota exceeded for metric: generate_content_free_tier_requests
limit: 0, model: gemini-2.0-flash
