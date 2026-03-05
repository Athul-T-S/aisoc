AI SOC Traffic Monitoring Project

Overview This project is a simple AI-assisted SOC prototype. It captures
network traffic from a machine using tshark, analyzes the traffic volume
per source IP, detects suspicious activity based on a packet threshold,
generates an alert, and sends that alert to Airia AI for investigation.

Main Features - Capture network traffic using tshark - Convert captured
packets (PCAP) to CSV - Analyze packet volume per source IP - Detect
suspicious traffic using a threshold - Generate SOC-style alert in JSON
format - Send the alert to Airia AI Agent API - Receive AI investigation
response

Project Files ai_soc_monitor.py -> Main Python script traffic.pcap ->
Captured traffic traffic.csv -> Parsed packet data alert.json ->
Generated alert airia_agent_instructions.txt -> Instructions for the
Airia AI agent

Requirements - Python 3 - tshark (Wireshark) - Python library: requests

Install dependency: pip install requests

Example Configuration INTERFACE = “eth0” CAPTURE_DURATION = 100
THRESHOLD = 40

AIRIA_API_URL = “INSERT AIRIA API URL HERE” AIRIA_API_KEY = “INSERT
AIRIA API KEY HERE”

How It Works 1. Capture network traffic using tshark. 2. Convert PCAP
traffic to CSV fields. 3. Count packets per source IP. 4. If packet
count exceeds the threshold, mark it as suspicious. 5. Generate an alert
JSON containing the indicator and evidence. 6. Send the alert to the
Airia AI Agent API for analysis.

Run the Project python3 soc.py

Purpose This project demonstrates how AI can assist SOC workflows by
automatically analyzing alerts and helping security analysts determine
whether activity is suspicious.
