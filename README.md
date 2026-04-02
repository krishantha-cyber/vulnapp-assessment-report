# Vulnerability Assessment Planning Assignment

**Target:** VulnApp Solutions Inc.  
**Application URL:** http://143.198.205.185/  
**Prepared By:** R.W.M. Chamod Krishantha Wanigasekara  

---

## 📄 Report
The full PDF report is included here:  
[📕 Vulnerability Assessment Planning Report.pdf](./Vulnerability Assessment Planning Report.pdf)

---

## 🔍 Key Passive Findings
- Publicly accessible **Admin Panel** (`/admin.php`) → 🔴 Critical
- **Profile page** exposes PII via IDOR (`/profile.php?id=`) → 🟠 High
- No **SSL/TLS encryption** → 🟡 Medium
- Verbose **login error messages** disclose system details → 🟡 Medium
- **HTML comments** in `/products.php` leak developer notes → 🔵 Low

---

## 📊 Risk Matrix
| Finding              | OWASP Category | Severity |
|----------------------|----------------|----------|
| Admin panel exposed  | A01 Broken Access Control | 🔴 Critical |
| Profile PII via IDOR | A01 Broken Access Control | 🟠 High |
| No SSL/TLS           | A02 Cryptographic Failures | 🟡 Medium |
| Verbose login errors | A03 Info Disclosure | 🟡 Medium |
| HTML comments        | A05 Security Misconfiguration | 🔵 Low |

---

## 🛠 Recommendations
- Restrict `/admin.php` behind authentication
- Implement SSL/TLS immediately
- Sanitize error messages
- Remove sensitive HTML comments
- Review access control design
