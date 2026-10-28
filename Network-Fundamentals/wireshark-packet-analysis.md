# Lab Write-Up: Traffic Analysis & Malicious Packet Inspection

## Overview
- **Target Topic:** PCAP Analysis & Protocol Inspection
- **Tools Used:** `wireshark`, `tshark`

## 1. Capture Summary
Analyzed a network packet capture file (`suspicious_traffic.pcap`) to inspect unencrypted HTTP authentication attempts and cleartext credentials.

## 2. Key Findings

### ⚠️ Cleartext Credential Exposure
- **Protocol:** HTTP (TCP Port 80)
- **Observed Behavior:** Application credentials were transmitted in cleartext via POST requests without TLS/SSL encryption.
- **Extracted Details:**
  - POST Endpoint: `/login.php`
  - Headers Disclosed: User-Agent details, Session Cookies.

## 3. Recommended Controls
1. Enforce HTTPS/TLS encryption across all authentication routes.
2. Implement Secure and HttpOnly flags on session cookies to prevent interception.
