# 🛡️ ReconRust - Reconnaissance CLI Tool for Web and Network Target

> 🎓 Final Year Project: Automated Recon Tool built with Rust  
> 🧠 Focused on security analysis, speed, and precision.  
> 🛠️ Covers multiple OWASP Top 10 vectors and real-world recon tasks.

---

## 📌 Features Overview

| Category | Feature | Description |
|---------|---------|-------------|
| 🎯 Target Setup | `--target`, `--url`, `--wordlist` | Define input for scanning modules |
| 🕵️ Passive Recon | WHOIS Lookup | Domain registrar, expiration info |
|  | DNS Lookup | A, MX, TXT, NS record resolution |
|  | Subdomain Enumeration | Discover subdomains with wordlist or API |
|  | IP/ASN/Geo Lookup | Identify hosting infrastructure |
|  | CDN / WAF Detection | Detect cloud/CDN service |
| 📡 Active Recon | TCP Port Scanning | Full port or common port scan |
|  | Banner Grabbing | Read raw service banner from ports |
|  | Service Detection | Identify services from banners |
| 🌐 Web Recon | HTTP Status Check | Validate HTTP response codes |
|  | Web Title & Headers | Extract page title and header metadata |
|  | TLS Certificate Info | Inspect SSL certs from targets |
|  | Directory Bruteforce | Discover hidden folders/files |
|  | Technology Detection | Guess framework/CMS from responses |
| 🛡️ Security Check | Insecure Headers | Detect missing HSTS, CSP, etc. |
|  | Default Pages | Find `/phpmyadmin`, `/server-status`, etc. |
|  | Login Page Finder | Locate admin/login portals |
|  | Injection Probe | Test basic SQLi/XSS with payloads |
| 📋 Reporting | JSON Export | Save output as structured `.json` |
|  | Markdown Report | Generate simple `.md` reports |
|  | OWASP Mapping | Highlight relevant OWASP categories |
| ⚙️ CLI & UX | Module Selection | `--modules portscan,dns,web` |
|  | Pretty Output | Color, tables, progress bar |
|  | Config File | Custom config (e.g. wordlists, timeout) |
|  | Thread Control | Support `--threads` for async scans |

---

## 🧠 OWASP Top 10 Mapping (2021)

| OWASP Category | Related Features |
|----------------|------------------|
| A01 - Broken Access Control | Login Finder, Admin Page Detection |
| A03 - Injection | SQLi/XSS Payload Probes |
| A05 - Security Misconfiguration | Missing headers, exposed default pages |
| A06 - Vulnerable Components | Tech detection + CVE tagging |
| A08 - Software Integrity Failures | TLS/cert inspection, headers |

---

## 🧱 Project Structure

```bash
reconrust/
├── src/
│   ├── main.rs              # CLI entry point
│   ├── modules/
│   │   ├── mod.rs
│   │   ├── portscan.rs
│   │   ├── dns.rs
│   │   ├── web.rs
│   │   ├── dirscan.rs
│   │   └── report.rs
├── wordlists/
│   └── common.txt
├── Cargo.toml
└── README.md
