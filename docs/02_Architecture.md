# Architecture

## Environment Overview

Project Sentinel is based on a fictional manufacturing company named **NorthRiver Timber Manufacturing**.

The environment represents a small industrial plant with separated Corporate IT and Operational Technology networks.

## High-Level Architecture

```text
                    Internet
                        |
                Corporate Firewall
                        |
                Corporate IT Network
                        |
                   OT Firewall
                        |
                Industrial Switch
                        |
        +---------------+----------------+
        |               |                |
Engineering WS      HMI Server        PLCs
        |               |                |
        +---------------+----------------+
                        |
                SPAN / Mirror Port
                        |
              Zeek Monitoring Sensor
                        |
                    Zeek Logs
                        |
                Splunk Enterprise
                        |
              SOC Dashboards & Alerts
