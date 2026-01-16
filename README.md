# Cloud-Fortress: Automated AWS Security Auditor

A Python-based security tool designed to automatically scan AWS Security Groups for dangerous "Open to World" configurations.

## 🛡️ Project Goal
In cloud networking, leaving Port 22 (SSH) open to `0.0.0.0/0` is a major security risk. This script automates the process of identifying these vulnerabilities across all security groups in a region.

## 🚀 Features
- **Automated Scanning**: Uses Boto3 to fetch and analyze AWS infrastructure.
- **Nested Data Parsing**: Navigates complex AWS JSON responses to extract CIDR and Port data.
- **Audit Logging**: Generates a `security_audit.txt` report for compliance and review.
- **Linux Ready**: Designed to run as a scheduled task (Cron Job) on Ubuntu.

## 🛠️ How to Use
1. **Clone the repo**: `git clone <your-repo-link>`
2. **Install requirements**: `pip install boto3`
3. **Configure AWS**: Run `aws configure` to provide your credentials.
4. **Run the tool**: `python3 fortress.py`

## 📊 Logic
The script applies the following logic filter:
- **Protocol**: TCP
- **Port**: 22
- **Source**: 0.0.0.0/0 (Global IPv4 Any)
