# Caleb Morrison | Cybersecurity Portfolio

CompTIA Security+ certified cybersecurity student at Collin College, completing my AAS in December 2026. I am pursuing entry-level SOC and cybersecurity analyst opportunities, with a focus on network visibility, log-ingestion troubleshooting, SIEM deployment, and clear technical documentation.

[LinkedIn](https://www.linkedin.com/in/caleb-morrison-cybersecurity) · [Labs](labs/README.md) · [Projects](projects/README.md)

## Featured Work

### [Security Onion: Restoring Zeek Telemetry](labs/security-onion-zeek-ingestion/README.md)

**Completed academic lab — September 2026**

Diagnosed an Elasticsearch mapping conflict that prevented Zeek logs from appearing in Hunt. Reloaded index templates, rolled over the data stream, and validated restored ingestion. The lab report recorded **2,697 indexed Zeek documents**; the included Hunt screenshot shows **1,108 connection events** in a 24-hour window.

**Demonstrates:** Linux troubleshooting, Elasticsearch mappings, data streams, network telemetry, and evidence-based validation.

### [Wazuh SIEM Deployment](labs/wazuh-siem-deployment/README.md)

**Server deployment complete — endpoint monitoring in progress**

Deployed an all-in-one Wazuh server on Ubuntu in VirtualBox and confirmed dashboard access. The saved dashboard shows no registered endpoint agents; Windows enrollment and controlled alert testing are the next milestones.

**Demonstrates:** SIEM installation, Linux service setup, virtual networking, and management access validation.

### [Structured Outputs Validation Pipeline](projects/structured-outputs-pipeline/README.md)

**Case study and results published — source and fixtures pending**

Built a Python pipeline with strict JSON Schema validation, one permitted repair attempt, and failure quarantine. The recorded eight-fixture test accepted two inputs immediately, repaired five, and rejected one. All seven accepted records passed revalidation.

**Demonstrates:** Defensive programming, error classification, bounded retries, failure isolation, and quality metrics.

## Skills Supported by These Projects

| Area | Hands-on work |
|---|---|
| Security monitoring | Security Onion, Zeek, Hunt queries, Wazuh deployment |
| Troubleshooting | Linux logs and services, Elastic Agent/Fleet, Elasticsearch mappings and data streams |
| Lab infrastructure | VMware Workstation, VirtualBox, Ubuntu Server, NAT and host-only networking |
| Programming | Python 3.12, JSON Schema validation, JSONL, repair limits and quarantine |
| Documentation | Root-cause analysis, screenshots, validation results, technical lab reports |

Coursework also covers TCP/IP, DNS, DHCP, subnetting, access control, Windows/Linux administration, risk management, and incident response.

## Education and Certifications

- **CompTIA Security+** — earned July 2026
- **Collin College, AAS in Cybersecurity** — expected December 2026
- **Cisco CCNA** — planned for early 2027
- Planning to continue into a Bachelor of Applied Technology program

I am transitioning from professional trucking into cybersecurity, bringing experience with regulated operations, accurate documentation, and communication under time pressure.

## Next Milestones

1. Enroll a Windows endpoint in Wazuh and document a controlled alert investigation.
2. Publish the original Python implementation, schema, fixtures, and offline reproduction steps.
3. Extend network investigations with documented findings and analyst recommendations.

## Repository Guide

- [labs/](labs/README.md) — Security Onion and Wazuh case studies with screenshot evidence
- [projects/](projects/README.md) — Python validation case study and recorded test results

All results describe academic or independent lab work. Each case study states its completed scope and remaining work.
