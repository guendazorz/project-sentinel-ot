# Project Sentinel – Executive Report

## Executive Summary

Project Sentinel is a passive Operational Technology (OT) network monitoring platform developed to demonstrate industrial network visibility using Zeek and Splunk Enterprise.

The project processes packet capture (PCAP) files, generates structured network telemetry with Zeek, establishes a baseline of normal network activity, and visualizes collected data through a Splunk dashboard.

The solution demonstrates the core phases of an OT monitoring deployment:

- Passive network monitoring
- Baseline traffic analysis
- Asset identification
- Security event visualization
- Detection engineering

---

# Objectives

The primary objectives of Project Sentinel were to:

- Deploy Zeek for passive industrial network monitoring.
- Analyze industrial PCAP files.
- Establish a network baseline.
- Integrate Zeek logs into Splunk.
- Develop an OT-focused monitoring dashboard.
- Create example detection use cases.

---

# Environment

| Component | Technology |
|-----------|------------|
| Operating System | Ubuntu (WSL2) |
| Network Monitor | Zeek 8.2 |
| SIEM | Splunk Enterprise |
| Version Control | Git & GitHub |
| Documentation | Markdown |

---

# Baseline Findings

The baseline analysis identified:

- Active industrial hosts
- Modbus communications
- HTTP traffic
- DNS activity
- File transfers
- Network service usage

These observations established a reference point for future anomaly detection.

---

# Dashboard Overview

The Splunk dashboard provides visibility into:

- Total monitored events
- Event distribution
- Industrial protocol activity
- Log sources
- Environment status
- Baseline metrics

---

# Detection Engineering

Five example detections were developed:

1. New Device Detection
2. Unusual Modbus Activity
3. Excessive DNS Activity
4. Unexpected External Communication
5. Network Activity Anomalies

These demonstrate how passive monitoring data can support OT security operations.

---

# Lessons Learned

Throughout the project several practical skills were developed:

- Zeek deployment
- Network traffic analysis
- Splunk administration
- SIEM data ingestion
- Dashboard creation
- Detection engineering
- GitHub project management
- Linux troubleshooting

A significant portion of the project involved resolving real-world configuration issues, particularly around Splunk indexing, data ingestion, and field parsing. These troubleshooting activities provided valuable experience with SIEM deployment and operational problem solving.

---

# Future Improvements

Potential future enhancements include:

- Live network packet capture
- Additional OT protocol support
- Automated Splunk alerts
- MITRE ATT&CK for ICS mapping
- Threat intelligence integration
- Custom Zeek detection scripts

---

# Conclusion

Project Sentinel successfully demonstrates an end-to-end passive OT monitoring workflow.

By combining Zeek, Splunk Enterprise, and structured documentation, the project provides a practical example of industrial network monitoring, baseline analysis, and detection engineering suitable for educational and portfolio purposes.
