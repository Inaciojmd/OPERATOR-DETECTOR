
# Ultimate Aggressive SNI Bypass Detector & Exploit Tool

https://img.shields.io/badge/python-3.7+-blue.svg
https://img.shields.io/badge/license-MIT-green.svg
https://img.shields.io/badge/platform-Linux%20%7C%20Windows%20%7C%20macOS-lightgrey.svg

## 🚀 Overview

Ultimate Aggressive SNI Bypass Detector & Exploit Tool is a professional-grade security assessment tool designed to identify and exploit SNI (Server Name Indication) TLS bypass vulnerabilities. This tool employs multiple aggressive techniques to detect misconfigured servers and automatically generates ready-to-use exploit configurations for various protocols.

## ⚡ Features

## 🔍 Detection Capabilities

· Multi-Technique SNI Bypass Detection - 6 different bypass methods
· Aggressive TLS Scanning - Comprehensive protocol and cipher suite testing
· DNS Intelligence - Complete DNS record analysis (A, AAAA, CNAME, MX, TXT, NS, SOA)
· Certificate Analysis - Detailed X.509 certificate inspection
· Live Connection Testing - Real-time socket-level validation

## 🛠️ Exploit Generation

· VLESS Configurations - Multiple optimized configurations
· VMess Protocols - Ready-to-deploy VMess setups
· Trojan Clients - Secure Trojan configurations
· Shadowsocks - Lightweight proxy configurations
· Automated Share Links - Instant deployment-ready URLs

## 🎯 Advanced Features

· High-Performance Scanning - Multi-threaded (up to 200 threads)
· Real-time Progress Monitoring - Color-coded progress with detailed statistics
· Comprehensive Reporting - JSON export with full scan metadata
· Security Rating System - Automated vulnerability assessment
· Configuration Export - Organized file structure for all generated exploits

📋 Prerequisites

System Requirements

· Python 3.7 or higher
· 2GB RAM minimum (4GB recommended)
· Network connectivity for target testing

🛠️ Installation

Method 1: Direct Download

```bash
git clone https://github.com/Inaciojmd/OPERATOR-DETECTOR
cd OPERATOR-DETECTOR
pip3 install -r requirements.txt
```

Method 2: Manual Setup

```bash
# Create virtual environment (recommended)
python -m venv daylor_env
source daylor_env/bin/activate  # Linux/macOS
# OR
daylor_env\Scripts\activate  # Windows
```

📖 Usage

Basic Syntax

```bash
python3 sni_detector.py -f domains.txt -t 100 -T 10 -v
```

# Command Line Options

Option Description Default
-f, --file Input file containing domains/subdomains (required) -
-t, --threads Number of concurrent threads 200
-T, --timeout Request timeout in seconds 10
-A, --aggressive Enable aggressive mode (always on) Enabled
-E, --exploit Generate exploit configurations (always on) Enabled
-v, --verbose Enable verbose logging Disabled

# Input File Format

Create a text file with one domain per line:

```
example.com
subdomain.example.org
target-domain.com
```

Example Usage

```bash
# Standard scan with 100 threads
python3 sni_detector.py -f targets.txt -t 100

# Verbose scan with custom timeout
python3 sni_detector.py -f domains.txt -t 50 -T 15 -v

# Maximum performance scan
python3 sni_detector.py -f subdomains.txt -t 200 -T 5
```

# 📊 Output

Generated Files

· ULTIMATE_RESULTS_TIMESTAMP.json - Complete scan results
· exploit_configs_TIMESTAMP/ - Directory containing all exploit configurations
  · domain_protocol.txt - Individual protocol configurations
  · Organized by domain and protocol type

Console Output

· Real-time progress with color-coded status
· Detailed statistics upon completion
· Security ratings for each domain
· Ready-to-use exploit links

# 🔧 Technical Details

Bypass Techniques Implemented

1. Direct IP + Host Header - Traditional IP-based access
2. Fake SNI + IP - Randomized SNI values
3. Empty SNI - SNI field omission
4. Random SNI - Dynamically generated SNI
5. Original SNI + IP - Legitimate SNI with IP targeting
6. No SNI + Custom Port - Port variation testing

Security Assessment

· SECURE - No bypass vulnerabilities detected
· MODERATE - Limited bypass capabilities
· VULNERABLE - Multiple bypass methods available
· CRITICAL - Immediate exploitation possible


# 📈 Performance Tips

· Adjust thread count based on your system capabilities
· Use appropriate timeout values for your network
· Monitor system resources during large scans
· Consider splitting large domain lists into batches

# 🐛 Troubleshooting

Common Issues

1. DNS Resolution Failures - Check network connectivity and DNS settings
2. SSL Context Errors - Ensure OpenSSL libraries are up to date
3. Memory Issues - Reduce thread count for large scans
4. False Positives - Verify results with manual testing

# ⚠️ Legal Disclaimer

This tool is intended for:

· Security research and education
· Authorized penetration testing
· Vulnerability assessment with proper permissions
· Academic research purposes

# Usage Restrictions:

· ❌ Do not use on networks without explicit authorization
· ❌ Do not use for malicious activities
· ❌ Do not violate local laws or regulations
· ❌ Ensure you have proper permissions before scanning

The developers are not responsible for misuse of this tool. Users assume all responsibility for ensuring their activities comply with applicable laws and regulations.

# 🛡️ Responsible Disclosure

If you discover vulnerabilities using this tool:

1. Notify the affected organization promptly
2. Provide detailed technical information
3. Allow reasonable time for remediation
4. Follow responsible disclosure practices

# 🔒 Security Considerations

· The tool disables SSL verification for testing purposes
· Generated configurations include allowInsecure flags
· Use in isolated testing environments only
· Review all generated configurations before deployment


