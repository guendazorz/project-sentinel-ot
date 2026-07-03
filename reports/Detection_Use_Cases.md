# Project Sentinel – Detection Use Cases

## Overview

The following detection use cases were developed as part of Project Sentinel to demonstrate how Zeek logs can be leveraged within Splunk to identify suspicious activity in an Operational Technology (OT) environment.

The detections are based on common security monitoring practices for industrial control systems and are intended to serve as examples of passive network monitoring rather than active prevention.

---

# Detection 1 – New Device Detected

## Objective

Identify hosts that have not previously communicated on the monitored OT network.

## Why It Matters

Unexpected devices may indicate:

- Unauthorized engineering workstations
- Rogue laptops
- Misconfigured equipment
- Potential attacker footholds

## Splunk Search

```spl
index=zeek
| stats count by source
```

## Expected Response

- Verify whether the device is authorized.
- Compare against the approved asset inventory.
- Investigate any unknown systems.

---

# Detection 2 – Unusual Modbus Activity

## Objective

Detect abnormal increases in Modbus communications.

## Why It Matters

A sudden increase in Modbus traffic may indicate:

- PLC scanning
- Unauthorized polling
- Malware communicating with industrial devices
- Misconfigured engineering software

## Splunk Search

```spl
index=zeek sourcetype=modbus
| timechart span=5m count
```

## Expected Response

- Review engineering activity.
- Confirm scheduled maintenance.
- Investigate unexpected spikes.

---

# Detection 3 – Excessive DNS Activity

## Objective

Identify unusually high DNS activity.

## Why It Matters

Industrial networks typically generate limited DNS traffic.

Large DNS volumes may indicate:

- Malware beaconing
- Command-and-control communication
- DNS tunneling
- Misconfigured applications

## Splunk Search

```spl
index=zeek source="*dns.log"
| timechart span=5m count
```

## Expected Response

- Identify the originating host.
- Review requested domains.
- Determine whether traffic is expected.

---

# Detection 4 – Unexpected External Communication

## Objective

Detect communications between internal OT assets and external IP addresses.

## Why It Matters

Industrial control systems should rarely communicate directly with Internet hosts.

Unexpected outbound connections could indicate:

- Malware
- Remote access tools
- Data exfiltration
- Configuration errors

## Splunk Search

```spl
index=zeek
NOT source="*modbus.log"
```

## Expected Response

- Validate firewall policies.
- Confirm whether the communication is authorized.
- Investigate unknown destinations.

---

# Detection 5 – Log Volume Anomaly

## Objective

Detect significant increases in overall monitoring events.

## Why It Matters

Rapid increases in network activity may indicate:

- Network scanning
- Broadcast storms
- Malware propagation
- Device malfunction

## Splunk Search

```spl
index=zeek
| timechart span=5m count
```

## Expected Response

- Identify affected systems.
- Review concurrent security events.
- Determine whether the increase is operational or malicious.

---

# Summary

These detection use cases demonstrate how Zeek network telemetry can be transformed into actionable security monitoring within Splunk.

Although the monitored environment is based on offline PCAP analysis, the same detection concepts can be applied to live OT environments to improve visibility and support Security Operations Center (SOC) workflows.
