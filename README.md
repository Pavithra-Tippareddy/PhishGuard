🛡️ PhishGuard — Phishing Email Detection Tool

[![Security](https://img.shields.io/badge/Security-Phishing%20Detection-red)](https://github.com/Pavithra-Tippareddy/PhishGuard)
[![Built With](https://img.shields.io/badge/Built%20With-HTML%2FJS-blue)](https://github.com/Pavithra-Tippareddy/PhishGuard)
[![Status](https://img.shields.io/badge/Status-Complete-green)](https://github.com/Pavithra-Tippareddy/PhishGuard)
[![Level](https://img.shields.io/badge/Level-Beginner%20Friendly-yellow)](https://github.com/Pavithra-Tippareddy/PhishGuard)
[![Course](https://img.shields.io/badge/Course-CyberStart%20by%20RigaTECHgirls-orange)](https://github.com/Pavithra-Tippareddy/PhishGuard)

> A browser-based phishing email analyser that helps anyone — technical or non-technical — identify whether an email is a phishing attempt before clicking anything.

---

## 🎯 What Is PhishGuard?

PhishGuard is a **security awareness tool** that analyses suspicious emails and produces an instant threat assessment with a risk score, plain-English explanations, and actionable recommendations.

Built as part of the **CyberStart** cybersecurity training program organised by **RigaTECHgirls** (EU Interreg Central Baltic Programme). The detection logic was designed directly from hands-on phishing investigation experience during a real-world case study scenario — the same DKIM failure and suspicious URL patterns that appeared in the case study became the core checks in this tool.

**No installation. No internet connection. No setup. Just open and use.**

---

## 🚀 How To Use It

1. Download **`phishing-detector.html`**
2. Open it in any web browser (Chrome, Firefox, Edge, Safari)
3. Enter the details of the suspicious email
4. Click **⚡ Analyse Email Threat**
5. Review your risk score, check results, and recommended actions

---

## 🔍 What It Analyses

The tool accepts the following inputs:

| Input | What To Enter |
|---|---|
| Sender Email Address | The full email address the message came from |
| Email Subject Line | The subject of the suspicious email |
| Link / URL | Any link or URL contained in the email |
| Email Body | Key content or phrases from the email body |
| Authentication Result | Whether SPF and DKIM passed or failed |
| Red Flag Checkboxes | Additional observations (urgency, credential request, etc.) |

---

## ✅ The 8 Detection Checks

PhishGuard runs **8 automated checks** and produces a threat score from 0–100:

| # | Check | What It Looks For | Risk Weight |
|---|---|---|---|
| 1 | 🔴 Sender Domain | Lookalike domains, suspicious TLDs (.lv .ru .tk), brand impersonation, hyphens | High |
| 2 | 🔴 Email Authentication | SPF and DKIM failures indicating spoofed or unverified sender | High |
| 3 | 🔴 Suspicious URL | Credential harvesting pages, login keywords, wrong domains, brand spoofing | High |
| 4 | 🟠 Urgency Language | Pressure tactics: "urgent", "action required", "account suspended", "expires" | Medium |
| 5 | 🔴 Credential Request | Any language asking you to sign in or enter your password via email | High |
| 6 | 🟠 Financial Keywords | Bank details, payment requests, invoice manipulation, salary references | Medium |
| 7 | 🔴 Suspicious Attachments | Macro-enabled files (.docm, .xlsm) and executables (.exe, .bat, .ps1) | High |
| 8 | 🟡 Additional Red Flags | Name mismatch, generic greetings, poor grammar, unexpected emails | Low–Medium |

---

## 🎯 Risk Levels

| Score | Rating | What To Do |
|---|---|---|
| 0–9 | ✅ Likely Safe | Exercise normal caution |
| 10–29 | 🟡 Low Risk | Verify sender through official channels |
| 30–49 | 🟠 Medium Risk | Do not click links — call sender directly |
| 50–74 | ⚠️ High Risk | Do not interact — report to IT/Security immediately |
| 75–100 | 🚨 Critical Threat | Report immediately — if already clicked, change passwords now |

---

## 🧠 Attack Techniques It Detects

PhishGuard identifies and explains the following real-world attack techniques:

| Technique | What It Means |
|---|---|
| **Domain Spoofing** | Fake domains designed to impersonate trusted brands (e.g. sharepoint-support.lv) |
| **Credential Harvesting** | Fake login pages that steal usernames and passwords |
| **Adversary-in-the-Middle (AiTM)** | Relay attack that intercepts sessions to bypass MFA entirely |
| **Business Email Compromise (BEC)** | Using compromised internal accounts to redirect payments or commit fraud |
| **Malicious Macro Delivery** | Malware hidden inside Office documents (.docm, .xlsm) |
| **Email Spoofing** | Forging the sender address to impersonate a trusted party |
| **Social Engineering** | Psychological pressure tactics designed to bypass critical thinking |
| **Display Name Spoofing** | Familiar display name combined with a malicious sender address |

---

## ⚙️ How The Detection Logic Works

PhishGuard uses three internal techniques — **no external database or internet connection required:**

### Technique 1 — Suspicious TLD List
Hardcoded list of country codes and domains frequently abused in phishing:
`.lv` `.ru` `.cn` `.tk` `.ml` `.ga` `.cf` `.gq` `.xyz` `.top` `.click`

### Technique 2 — Brand Keyword List
Checks if a sender or URL contains a major brand name but is NOT on that brand's real domain:
`microsoft` `sharepoint` `google` `paypal` `amazon` `apple` `docusign` `dropbox` `netflix` `office365`

### Technique 3 — Pattern Matching
Scans for known phishing patterns in sender, URL, subject, and body:
- Hyphens in domains: `sharepoint-documents-login.lv`
- Login keywords in URLs: `/login` `/signin` `/verify` `/auth`
- Urgency words: `urgent` `action required` `expires` `account suspended`
- Financial words: `bank detail` `invoice` `transfer` `salary`

---

## ⚠️ Limitations

PhishGuard is a **security awareness and education tool** — not a production enterprise solution:

| Limitation | What A Real Tool Would Do Instead |
|---|---|
| Hardcoded static rules | Live threat intelligence (VirusTotal, PhishTank, Spamhaus) updated in real time |
| No machine learning | AI model trained on millions of phishing emails |
| Manual user input | Automatic email header parsing |
| No automated response | Auto-quarantine emails + SOC alerting |
| 10 brands / 11 TLDs | Millions of known malicious domains |

### Real Enterprise Tools That Do This At Scale
- **Microsoft Defender for Office 365** — Safe Links, Safe Attachments, real-time URL detonation
- **Proofpoint** — ML-based detection, BEC protection, threat intelligence feeds
- **Mimecast** — Email filtering, URL rewriting, impersonation protection
- **VirusTotal** — Free URL and file scanning against 70+ security engines

---

## 🧪 Test It With A Real Example

Try entering the phishing email from the CyberStart case study:

| Field | Value |
|---|---|
| Sender | `training-documents@sharepoint-support.lv` |
| Subject | `Updated participant payment list` |
| URL | `https://sharepoint-documents-login.lv/payment-list` |
| Auth Result | SPF passed — DKIM failed |
| Checkboxes | Financial content, Credential request |

**Expected result: 🚨 CRITICAL THREAT**

---

## 📁 Repository Contents

```
PhishGuard/
├── phishing-detector.html    ← Complete working tool (open in any browser)
└── README.md                 ← This file
```

---

## 🎓 Learning Context

This tool was built during the **CyberStart** cybersecurity training program organised by **RigaTECHgirls**, co-funded by the EU Interreg Central Baltic Programme.

The detection logic came directly from investigating a phishing case study covering:
- Phishing email delivery and DKIM/SPF failure analysis
- Adversary-in-the-Middle (AiTM) credential theft and MFA bypass
- OAuth persistence via offline_access permission
- Business Email Compromise (BEC) fraud attempt targeting Finance
- Malicious macro (.docm) delivery blocked by EDR
- GDPR personal data breach implications

The same red flags identified in that investigation — suspicious sender domain, DKIM failure, credential harvesting URL, financial keywords — became the core detection checks in PhishGuard.

---

## 👤 About The Author

**Pavithra Tippareddy** — IT professional transitioning into cybersecurity.

- 3+ years enterprise network engineering experience (Accenture)
- ISC2 Certified in Cybersecurity (CC)
- Google Cybersecurity Professional Certificate
- Currently completing CyberStart by RigaTECHgirls (June 2026)
- Based in Helsinki, Finland — EU/EEA work rights

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/pavithra-b-t-1a3118154)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-black)](https://github.com/Pavithra-Tippareddy)

---

*Built for educational purposes as part of the CyberStart cybersecurity training program by RigaTECHgirls.*
