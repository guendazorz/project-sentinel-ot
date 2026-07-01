# Detection Strategy

## Purpose

This document defines the initial detection logic for Project Sentinel.

The goal is to identify suspicious activity in an OT environment using Zeek logs and Splunk searches.

## Detection Priorities

| Detection Use Case | Severity | Rationale |
|---|---|---|
| New OT device observed | Medium | Unknown devices may indicate unauthorized access or misconfigured equipment |
| PLC communicating externally | Critical | PLCs should not normally communicate directly with the internet |
| New TCP/102 communication | High | TCP/102 is commonly associated with Siemens S7 PLC communication |
| New Modbus/TCP communication | High | Unexpected Modbus traffic may indicate unauthorized industrial access |
| Port scanning behavior | High | Scanning can indicate reconnaissance before an attack |
| Excessive DNS requests | Medium | May indicate misconfiguration, malware, or unusual host behavior |
| New engineering workstation activity | Medium | Engineering workstations can modify PLC logic and require monitoring |
| Unusual connection volume | Medium | Large spikes may indicate scanning, malfunction, or suspicious automation |

## Evidence Model

Each finding should include:

| Field | Description |
|---|---|
| Observation | What was observed |
| Evidence | Log source, command, or Splunk search supporting the observation |
| Confidence | High, Medium, or Low |
| Recommendation | Suggested next action |

## Example Finding Format

| Observation | Evidence | Confidence | Recommendation |
|---|---|---|---|
| Repeated TCP/102 traffic observed | conn.log shows repeated connections to destination port 102 | High | Validate destination asset with engineering team and monitor as PLC candidate |

## Initial Splunk Detection Ideas

- Detect first-time-seen source IPs
- Detect traffic to industrial ports
- Detect external communication from OT assets
- Detect high connection counts from one source
- Detect DNS activity from OT hosts
- Detect rejected or failed connections
