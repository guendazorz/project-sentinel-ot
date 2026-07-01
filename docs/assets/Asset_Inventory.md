# Asset Inventory

## Purpose

This asset inventory tracks systems observed or represented in Project Sentinel.

Asset roles are assigned based on available evidence, expected OT architecture, and analyst confidence.

## Initial Asset Inventory

| Asset Name | IP Address | Role | Criticality | Confidence | Evidence |
|---|---|---|---|---|---|
| PLC-01 | 10.10.10.10 | Siemens PLC Candidate | Critical | High | Receives repeated TCP/102 traffic |
| ENG-01 | 10.10.10.30 | Engineering Workstation Candidate | High | Medium | Initiates majority of TCP/102 communications |
| ENG-02 | 10.10.10.20 | Engineering Workstation Candidate | High | Medium | Initiates TCP/102 communication |
| DNS-01 | 192.168.89.2 | DNS Resolver / Infrastructure Host | Medium | High | Performs DNS communication with 8.8.8.8 |
| GW-01 | 192.168.88.1 | Gateway Candidate | Medium | Medium | Receives local subnet traffic |
| EXT-DNS | 8.8.8.8 | External DNS Server | External | High | Known Google DNS resolver |

## Notes

Asset roles are updated as more evidence is collected.

Confidence levels:

- High: Strong evidence supports the role
- Medium: Role is likely but requires validation
- Low: Role is speculative
