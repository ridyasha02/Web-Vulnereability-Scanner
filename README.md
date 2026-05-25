# Web Application Security Scanner

## Introduction

The **Web Application Security Scanner** is a powerful platform designed to simplify vulnerability assessment for web applications. Built with Flask and integrated with OWASP ZAP, the system provides an intuitive interface for scanning websites, identifying security flaws, generating detailed reports, and securely storing results in AWS S3.

---

## Key Capabilities

- **Automated Security Scanning**  
  Uses OWASP ZAP to perform spidering, passive analysis, and active vulnerability testing with live progress updates.

- **Comprehensive Report Generation**  
  Produces scan reports in multiple formats including PDF, JSON, and CSV for easy analysis and sharing.

- **Cloud-Based Report Storage**  
  Securely uploads generated reports to AWS S3 for centralized access and management.

- **Interactive Web Dashboard**  
  Offers a clean Flask-powered interface for launching scans, monitoring activity, and reviewing findings.

- **Flexible Architecture**  
  Easily customizable templates and modular design allow seamless extension for additional features and integrations.

- **Built-In Security Practices**  
  Implements secure API key handling, input sanitization, and other protections to enhance operational safety.

---

# Table of Contents

1. [Requirements](#requirements)
2. [Setup Instructions](#setup-instructions)
3. [Using the Scanner](#using-the-scanner)
4. [System Workflow](#system-workflow)
5. [Future Enhancements](#future-enhancements)
6. [Contribution Guidelines](#contribution-guidelines)
7. [License](#license)

---

# Requirements

Before setting up the project, ensure the following are available:

1. Python 3.8 or later  
2. OWASP ZAP installed and running locally or remotely  
3. An AWS account with an S3 bucket configured  
4. Valid API credentials for OWASP ZAP and AWS services  
5. (Optional) A Python virtual environment for dependency isolation  

---

# Setup Instructions

## 1. Clone the Repository

```bash
git clone https://github.com/yourusername/web-app-security-scanner.git
cd web-app-security-scanner
```

## 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

### Linux / macOS

```bash
source venv/bin/activate
```

### Windows

```bash
venv\Scripts\activate
```

## 3. Install Required Dependencies

```bash
pip install -r requirements.txt
```

## 4. Configure Environment Variables

Create a `.env` file in the project root directory:

```env
ZAP_API_KEY=your_zap_api_key
S3_BUCKET_NAME=your_bucket_name
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
```

## 5. Launch the Application

```bash
flask run
```

The application will be available at:

```text
http://127.0.0.1:5000/
```

---

# Using the Scanner

## Start a Scan

1. Open the web application in your browser.  
2. Enter the target website URL.  
3. Initiate the scan process.  
4. Monitor scan progress in real time.  
5. Review detected vulnerabilities after completion.  

## Access Reports

- Generated reports are stored in AWS S3.
- Users can browse and open reports directly from the dashboard.
- Reports can be downloaded in:
  - PDF
  - JSON
  - CSV

---

# API Endpoints

## Scan Target

**Endpoint**

```http
POST /scan
```

**Request Body**

```json
{
  "target_url": "http://example.com"
}
```

---

## View Reports

**Endpoint**

```http
GET /view-report
```

**Parameters**

```text
report_name=<report_filename>
```

---

# System Workflow

## 1. Website Crawling

The scanner begins by spidering the target application to identify accessible URLs and endpoints.

## 2. Vulnerability Assessment

OWASP ZAP performs:

- Passive Scanning
- Active Scanning
- Security Rule Analysis

## 3. Report Creation

Collected findings are converted into:

- PDF reports
- JSON files
- CSV summaries

## 4. Secure Storage

Generated reports are uploaded to AWS S3 for centralized and secure storage.

## 5. User Visualization

The Flask dashboard displays vulnerabilities and provides report download options.

---

# Future Enhancements

## 1. Multi-Tool Integration

Expand support for additional security tools such as:

- Burp Suite
- Nessus
- Nmap

## 2. Advanced Analytics Dashboard

Introduce interactive charts, graphs, and vulnerability trend analysis.

## 3. Scheduled Scanning

Enable recurring automated scans with alert notifications.

## 4. User Authentication & RBAC

Implement secure login systems and role-based access control.

## 5. Threat Intelligence Support

Integrate external threat intelligence feeds to enrich vulnerability reports.

## 6. Docker Deployment

Containerize the application for simplified deployment and scalability.

## 7. Multi-Cloud Compatibility

Add support for:

- Google Cloud Storage
- Azure Blob Storage

---


