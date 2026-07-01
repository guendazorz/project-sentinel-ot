# Monitoring Strategy

## Purpose

The purpose of Project Sentinel is to improve visibility into Operational Technology (OT) network traffic by using Zeek and Splunk to collect, analyze, and visualize network activity.

This strategy defines what should be monitored and why.

## Monitoring Objectives

| Objective | Description |
|---|---|
| Asset Discovery | Identify devices communicating on the OT network |
| Network Baseline | Understand normal traffic patterns between OT assets |
| Industrial Protocol Visibility | Monitor industrial protocol activity such as TCP/102, Modbus, DNP3, and related services |
| Suspicious Communication Detection | Identify unusual or unauthorized communications |
| SOC Visibility | Provide dashboards for analysts to quickly understand OT activity |
| Incident Investigation | Support evidence-based reporting and recommendations |

## Key Data Sources

| Source | Purpose |
|---|---|
| Zeek conn.log | Connection metadata, hosts, ports, protocols, byte counts |
| Zeek dns.log | DNS queries and external name resolution |
| Zeek notice.log | Zeek-generated notices and suspicious activity |
| Zeek weird.log | Protocol anomalies and unusual behavior |
| Splunk Dashboards | Visualization and investigation workflow |

## Analyst Questions

The monitoring workflow should help answer:

- What devices are communicating?
- Which devices are most active?
- Which services and ports are being used?
- Are industrial protocols present?
- Are PLCs communicating with unexpected systems?
- Are any devices communicating externally?
- Is there evidence of scanning or reconnaissance?
- What should be investigated further?

## Monitoring Scope

This project focuses on passive network monitoring. Zeek observes traffic from packet captures or mirrored network traffic.

Zeek does not actively scan, probe, or interfere with OT systems.
