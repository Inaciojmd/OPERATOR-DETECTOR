# Ultimate Aggressive SNI Bypass Detector & Exploit Tool

![python](https://img.shields.io/badge/python-3.7+-blue.svg) ![license](https://img.shields.io/badge/license-MIT-green.svg) ![platform](https://img.shields.io/badge/platform-Linux%20%7C%20Windows%20%7C%20macOS-lightgrey.svg)

---

## 🚀 Overview

**Ultimate Aggressive SNI Bypass Detector & Exploit Tool** is a professional security assessment utility designed to detect Server Name Indication (SNI) TLS bypass misconfigurations and optionally generate configuration payloads for testing common proxy/client protocols. The tool automates aggressive detection techniques, TLS analysis, DNS intelligence, and can output organized exploit/configuration files for authorized testing.

> **WARNING:** This tool can be misused. Use only for authorized security research, penetration testing with explicit permission, or educational purposes. Always comply with applicable laws and organizational policies.

---

## ⚡ Key Features

### Detection
- Multi-technique SNI bypass detection (6 methods)
- Aggressive TLS scanning (protocols and cipher suites)
- DNS intelligence (A, AAAA, CNAME, MX, TXT, NS, SOA)
- X.509 certificate inspection
- Real-time socket-level connection testing

### Optional Exploit Configuration Generation
- VLESS configurations
- VMess configurations
- Trojan client configs
- Shadowsocks configs
- Automated share links for quick deployment

### Additional
- Multi-threaded scanning (default up to 200 threads)
- Real-time progress monitoring (color-coded)
- JSON export with full scan metadata
- Automated security rating per host
- Organized output directory for generated configs

---

## 📋 Requirements

- Python 3.7 or newer
- Minimum 2 GB RAM (4 GB recommended)
- Network access for target testing
- Up-to-date OpenSSL & Python TLS bindings (e.g. `pyOpenSSL`)

---

## 🛠️ Installation

**Method 1 — Clone and install**
```bash
git clone https://github.com/Inaciojmd/OPERATOR-DETECTOR
cd OPERATOR-DETECTOR
pip3 install -r requirements.txt
```

**Method 2 — Virtual environment (recommended)**
```bash
python -m venv daylor_env
# Linux / macOS
source daylor_env/bin/activate

# Windows (PowerShell)
.\daylor_env\Scripts\Activate.ps1
# or (cmd)
daylor_env\Scripts\activate

pip3 install -r requirements.txt
```

---

## 📖 Usage

**Basic syntax**
```bash
python3 sni_detector.py -f domains.txt -t 100 -T 10 -v
```

**Command-line options**
| Option | Description | Default |
|---|---|---:|
| `-f, --file` | Input file with domains/subdomains (one per line) | **Required** |
| `-t, --threads` | Number of concurrent worker threads | `200` |
| `-T, --timeout` | Request timeout in seconds | `10` |
| `-A, --aggressive` | Enable aggressive testing (explicit flag) | **disabled** |
| `-E, --exploit` | Generate exploit/config files (explicit flag) | **disabled** |
| `-v, --verbose` | Enable verbose logging | disabled |

> For safety, `--aggressive` and `--exploit` are **disabled by default**. Enable them only when you have authorization and understand the risk.

**Input file format**
```
example.com
subdomain.example.org
target-domain.com
```

**Examples**
```bash
# Standard scan with 100 threads
python3 sni_detector.py -f targets.txt -t 100

# Verbose scan with custom timeout
python3 sni_detector.py -f domains.txt -t 50 -T 15 -v

# Maximum performance scan with aggressive tests and exploit generation
python3 sni_detector.py -f subdomains.txt -t 200 -T 5 -A -E
```

---

## 📊 Output

**Files produced**
- `ULTIMATE_RESULTS_<TIMESTAMP>.json` — Full JSON results
- `exploit_configs_<TIMESTAMP>/` — Generated exploit/config files (if `-E` enabled)
- `domain_protocol.txt` — Per-domain protocol details
- Output directory structured by domain and protocol

**Console output**
- Real-time progress with color-coded statuses
- Final statistics and security rating per domain

---

## 🔧 Implemented Bypass Techniques
- **Direct IP + Host Header** — IP access with a custom Host header
- **Fake SNI + IP** — Send randomized SNI value to the IP
- **Empty SNI** — Omit the SNI field entirely
- **Random SNI** — Dynamically generated random SNI values
- **Original SNI + IP** — Use the legitimate SNI while targeting the IP
- **No SNI + Custom Port** — Test alternative ports without SNI

**Security rating categories**: `SECURE`, `MODERATE`, `VULNERABLE`, `CRITICAL`.

---

## 📈 Performance Tips
- Lower thread count if you see high CPU or memory usage
- Increase timeout for slow or rate-limited networks
- Run large lists in batches to avoid resource exhaustion

---

## 🐛 Troubleshooting
- **DNS resolution failures** — Verify network and DNS resolver configuration
- **OpenSSL / SSL context errors** — Ensure OpenSSL and Python bindings (`pyOpenSSL`, `cryptography`) are installed and up-to-date
- **Memory issues** — Reduce threads or process targets in smaller batches
- **False positives** — Confirm critical findings with manual, non-aggressive tests

---

## ⚖️ Legal & Ethical Notice
This tool is intended for:
- Security research and education
- Authorized penetration testing (with explicit permission)
- Academic vulnerability assessment

**Do not use this tool** on systems or networks without explicit authorization. Unauthorized scanning or exploitation may be illegal and subject to penalties. The authors and maintainers are not responsible for misuse.

---

## 🛡️ Security Considerations
- SSL verification may need to be disabled for some tests; disable it only in isolated test environments
- Generated configs may include `allowInsecure` flags — always review before use
- Store scan results and exploit configs securely

---

## 🔒 Responsible Disclosure
If you find a vulnerability during testing:
1. Notify the affected organization promptly.
2. Provide technical details to reproduce the issue.
3. Allow reasonable time for remediation before public disclosure.
4. Follow coordinated disclosure best practices.

---

