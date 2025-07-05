# 🛡️ CVE-2024-28623 – XSS Vulnerability in RiteCMS v3.0.0

## 🔍 Overview

This repository documents a **Cross-Site Scripting (XSS)** vulnerability discovered in **RiteCMS v3.0.0**, which I reported and was assigned the CVE ID **CVE-2024-28623**.

---

## 📄 Vulnerability Details

- **CVE ID**: [CVE-2024-28623](https://nvd.nist.gov/vuln/detail/CVE-2024-28623)
- **Product**: RiteCMS
- **Version Affected**: v3.0.0
- **Vulnerability Type**: Reflected Cross-Site Scripting (XSS)
- **Vulnerable Component**: `main_menu/edit_section`
- **Status**: Publicly disclosed on NVD

---

## ⚠️ Impact

The XSS vulnerability allows an attacker to execute arbitrary JavaScript in the victim’s browser, leading to:

- Credential or session token theft  
- Phishing attacks via fake forms or redirects  
- Full control over the victim’s session (browser-based)  
- Potential privilege escalation (depending on context)

---

## 💥 Proof of Concept (PoC)

### 🔧 Payload

```html
'"><svg/onload=confirm(/xsss/)>
```

This payload demonstrates a basic reflected XSS vector that triggers a JavaScript `confirm()` dialog when rendered unsanitized.

---

### 📹 PoC Video Demonstration


https://github.com/user-attachments/assets/c7254309-157b-4986-b1a1-737f50ade5bf


> ✅ This video demonstrates how the XSS vulnerability in RiteCMS v3.0.0 is triggered using the payload.

---

## 🛡️ Mitigation Recommendations

- ✅ **Input Validation**: Properly sanitize and encode all user input rendered in HTML.  
- ✅ **Patch CMS**: Upgrade to a patched version when available.  
- ✅ **Security Headers**: Implement CSP (Content Security Policy) to restrict script execution.  
- ✅ **WAF**: Use a Web Application Firewall to detect and block common XSS payloads.  

---

## 👨‍💻 Researcher Info

**Discovered & Reported By:** [@GURJOTEXPERT](https://github.com/GURJOTEXPERT)  
**CVE Link:** [CVE-2024-28623](https://nvd.nist.gov/vuln/detail/CVE-2024-28623)  
**Contact:** For questions or collaboration, open an issue or message via GitHub.  

---

## 📬 Disclaimer

This repository is published for educational and research purposes only. Do not attempt to exploit this vulnerability on systems you do not own or have explicit permission to test.
