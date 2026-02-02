# IT Maintenance & Operations Log: GTS

## 📋 The Standard Operating Procedure (SOP)
### Weekly (Mondays)
- [x] **Identity Audit:** Review [Entra Sign-in logs](https://entra.microsoft.com) (Failed logins/unusual locations).
- [x] **Automation Check:** Verify Power Automate flow status (Check [Run history](https://make.powerautomate.com)).
- [x] **Email Flow:** External email test (Gmail -> Business email). Verify receipt in SharePoint Tracker.
- [x] **Identity Posture:** Record [Identity Secure Score](https://entra.microsoft.com) (Protection > Identity Secure Score).
- [x] **Global Posture:** Record [M365 Secure Score](https://security.microsoft.com/securescore) (Defender Portal).
- [x] **Web Uptime:** Verify [guestturnoversolutions.co.uk](https://guestturnoversolutions.co.uk) loads with active HTTPS.

### Monthly (First Monday)
- [ ] **DR Test:** Verify Break-glass account access (Login test).
- [ ] **Analytics:** Review Google Analytics traffic trends.
- [ ] **Governance:** Audit SharePoint folder permissions.

---

## 🗓️ 2026 Maintenance Tracker

| Date | Week | Status | M365 Score | Identity Score | Key Actions / Observations |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 05 Jan | WK1 | ✅ Healthy | 45.0%* | 58.3% | Initial baseline. *Estimated based on Jan 30 audit. |
| 12 Jan | WK2 | ✅ Healthy | 45.0%* | 58.3% | Routine check. Verified SPF/DKIM via MXToolbox. |
| 19 Jan | WK3 | ✅ Healthy | 45.0%* | 58.3% | Routine check. Reviewed Entra ID sign-in logs. |
| 26 Jan | WK4 | ⚠️ Incident | 45.0%* | 58.3% | **Phase 2 Deploy.** Automation delay noted  |
| 02 Feb | WK5 | ✅ Healthy | 45.96% | 58.33% | **Today:** Logged actual Defender baseline.  |
| 09 Feb | WK6 | | | | |

---

## 💡 Status Key
- ✅ **Healthy:** All systems operational.
- ⚠️ **Incident:** Technical hurdle encountered (See Incident Log).
- ❌ **Fault:** Service down/Critical failure.
