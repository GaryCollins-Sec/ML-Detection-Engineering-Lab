# SOC Automation Lab

## Objective

Engineered an automated security orchestration pipeline to streamline the triage of suspicious network connections. By integrating Wazuh as the primary XDR/SIEM and Shuffle SOAR for workflow automation, I successfully eliminated manual reputation lookups. This system delivers pre-enriched alerts directly to analysts, significantly reducing Mean Time to Respond (MTTR) and allowing for immediate, data-driven decision-making.

### Skills Learned

- Log Ingestion & Normalization: Configured Rsyslog to stream logs and used Wazuh to normalize diverse data sources (network vs. host) into a unified format.

- Kernel-Level Auditing: Implemented auditd on Linux to capture low-level system calls (execve, connect, open), providing the deep telemetry necessary for behavioral analysis.

- API Integration: Connected Shuffle SOAR to the Wazuh API to fetch alerts in real-time.

- Containerization: Deployed and managed the SOAR platform using Docker, demonstrating an understanding of microservices architecture.

- Attack Simulation: Used Kali Linux to execute real-world attack vectors, including brute force, privilege escalation, and lateral movement, to validate detection efficacy.

- Virtual Infrastructure: Managed a multi-node lab environment using different OS flavors (Ubuntu, Kali) and specialized appliances (Wazuh OVA).

### Tools Used

- Wazuh (OVA): Served as the central Security Information and Event Management (SIEM) platform for log aggregation, indexing, and alerting.

- Rsyslog: Acted as the high-speed log transport protocol to stream telemetry from endpoints to the Wazuh manager.

- Shuffle (Docker-based): A Security Orchestration, Automation, and Response (SOAR) platform used to build workflows that ingest Wazuh alerts and trigger response actions.

- Docker: Used to containerize and manage the Shuffle environment, ensuring a portable and scalable automation backend.

- Ubuntu: The "Victim VM" where auditd and the Wazuh agent were deployed to provide data for analysis.

- Kali Linux: The "Adversary VM" used to simulate real-world attacks like brute-forcing, lateral movement, and data exfiltration.

- Ubuntu Server (Host): Acted as the high-performance backbone for the security stack, configured as a headless orchestration node to manage the SOAR backend and ML processing.
  


## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.
