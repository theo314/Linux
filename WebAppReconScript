#!/bin/bash

# Define the target URL
TARGET_URL="https://blog.offgridtech.xyz"

# Define the file for the recon report
REPORT_FILE="$HOME/Documents/recon_report"

# Run WHOIS and append output to the report
echo "WHOIS Report for $TARGET_URL" >> "$REPORT_FILE"
whois $(echo $TARGET_URL | awk -F/ '{print $3}') >> "$REPORT_FILE"
echo -e "\n\n" >> "$REPORT_FILE"

# Run SSLyze and append output to the report
echo "SSLyze Report for $TARGET_URL" >> "$REPORT_FILE"
sslyze $TARGET_URL >> "$REPORT_FILE"
echo -e "\n\n" >> "$REPORT_FILE"

# Run Nmap and append output to the report
echo "Nmap Report for $TARGET_URL" >> "$REPORT_FILE"
nmap -A $(echo $TARGET_URL | awk -F/ '{print $3}') >> "$REPORT_FILE"
echo -e "\n\n" >> "$REPORT_FILE"

# Run WhatWeb and append output to the report
echo "WhatWeb Report for $TARGET_URL" >> "$REPORT_FILE"
whatweb -v $TARGET_URL >> "$REPORT_FILE"
echo -e "\n\n" >> "$REPORT_FILE"

# Run WPScan and append output to the report
echo "WPScan Report for $TARGET_URL" >> "$REPORT_FILE"
wpscan --url $TARGET_URL --api-token YOUR_API_TOKEN_HERE >> "$REPORT_FILE"
echo -e "\n\n" >> "$REPORT_FILE"

# Complete
echo "Reconnaissance report saved to $REPORT_FILE"
