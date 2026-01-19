# Siem Home Lab

## Objective
This project involved building a controlled Security Operations Center (SOC) home lab environment. I deployed a Wazuh SIEM to monitor a "victim" Ubuntu machine and simulated real-world attack vectors using Kali Linux. The goal was to configure log ingestion, analyze security events, and tune detection rules to identify malicious activity.

### Skills Learned
- Deployment & Enrollment: You learned how to deploy a complex SIEM (Wazuh) and enroll endpoints using agents. This demonstrates I can manage the "plumbing" of a security stack.
- Rule Tuning & Noise Reduction: One of the most valued skills in a SOC is the ability to "silence the noise." By identifying and suppressing Rule 510, you demonstrated that you can prevent alert fatigue and focus on high-fidelity threats.
- Custom Rule Creation: You learned how to write and modify XML rules to escalate security levels based on frequency and timeframe— essential for catching sophisticated brute-force attacks.
- Tool Proficiency: I gained hands-on experience with Hydra and Nmap, the industry standards for password cracking and network discovery.
- Attack Patterns: I didn't just run a command; you learned what those attacks look like "on the wire" and in the logs. This "Attacker Mindset" helps me become a better defender.
- Mapping to MITRE ATT&CK: I learned to categorize alerts using a professional framework.
- Log Correlation: I practiced "connecting the dots" between a source IP in Kali and a failed login event on Ubuntu. This is the core of incident investigation.
- Virtual Networking: I successfully managed communication between three different VMs (Kali, Ubuntu, and Wazuh OVA), which requires an understanding of IP addressing, subnets, and host-only networking.


### Tools Used
- Wazuh (SIEM/XDR): Centralized log management, correlation, and intrusion detection.
- Wazuh Agent: Installed on the endpoint to monitor system logs (auth.log), file integrity, and running processes.
- Kali Linux: The primary offensive platform used for adversary emulation.
- Hydra: High-speed network logon cracker used to simulate SSH brute-force attacks.
- Nmap (Network Mapper): Used for network discovery and security auditing to trigger "multiple connection" alerts.
- Oracle VirtualBox: Hosted the virtualized lab environment.
- Ubuntu Server 24.04: Acted as the victim/target endpoint.
- Linux CLI / Bash Scripting: Used for automated log generation, rule configuration, and system administration.
  


## Steps


Reference: SIEM 1


<img width="642" height="486" alt="Ubuntu_check" src="https://github.com/user-attachments/assets/1574ad30-3ef6-40b7-aff5-339be70ddb97" />




In this phase of the project, I used the Linux command line on the Ubuntu-Victim endpoint to verify its network configuration and IP address. By executing the ip a command, I confirmed the agent's network identity, ensuring a stable connection within the isolated lab environment for log forwarding to the Wazuh Manager. This step was critical for validating that the endpoint's telemetry was correctly attributed to the specific target during the simulated attack and monitoring phases.


Reference: SIEM 2




<img width="341" height="143" alt="ping" src="https://github.com/user-attachments/assets/50e0552d-6493-458b-8c36-44f4259f441d" />




In this final phase of the project, I used the Kali Linux terminal to conduct network reconnaissance and verify connectivity to the target. By executing a targeted ping command to the Ubuntu-Victim IP address, I confirmed active communication and low latency within the isolated virtual network. This established the necessary baseline for launching simulated attacks, such as Hydra brute-forcing and Nmap scanning, which I subsequently monitored through the Wazuh SIEM to validate detection and response capabilities.





Reference: SIEM 3




<img width="358" height="402" alt="Nmapscan" src="https://github.com/user-attachments/assets/42b6531b-be32-43d5-8657-4de85364c1c9" />




I utilized Nmap 7.94SVN on my Kali Linux machine to conduct an aggressive scan of the target endpoint. By executing the nmap -A -T4 command, I performed simultaneous OS detection, service versioning, and traceroute analysis to map the attack surface of the Ubuntu-Victim. The scan successfully identified the target as an Oracle VirtualBox virtual NIC with a rapid response time of 0.0014s latency, confirming the high-speed connectivity within my isolated lab environment. This activity was designed to trigger "Multiple connection attempts" alerts within the Wazuh SIEM, allowing me to verify that the manager could distinguish between standard network traffic and active scanning behavior.



Reference: SIEM 4


<img width="331" height="71" alt="Hydra" src="https://github.com/user-attachments/assets/9c7fa96b-13f8-464f-bb1d-afe46fd1010b" />


In this final execution phase, I utilized Hydra v9.5 on my Kali Linux machine to perform a simulated SSH brute-force attack against the target endpoint. By targeting the root user and leveraging the industry-standard rockyou.txt wordlist, I attempted to force an authentication breakthrough to test the SIEM's detection capabilities. This active exploit was designed to trigger high-severity alerts within Wazuh, allowing me to verify the system's ability to identify and log rapid-fire credential-stuffing attempts in real time.



Reference: SIEM 5


<img width="1572" height="720" alt="Screenshot 2026-01-18 190811" src="https://github.com/user-attachments/assets/b665903d-a371-4014-adc0-02a6dadfbad0" />


In this project, I engineered a SOC Home Lab using Wazuh SIEM to monitor and analyze real-world cyberattacks. By integrating an Ubuntu 24.04 agent, I enabled real-time log ingestion and kernel-level monitoring. I simulated a high-frequency SSH brute-force attack using Hydra, which the manager successfully detected as a Level 10 (High Severity) event. The dashboard validates the transition from raw logs to actionable intelligence, mapping the attack to MITRE ATT&CK T1110 (Brute Force) and providing a visual timeline of the incident for rapid response and compliance reporting.




Reference: SIEM 6


<img width="1566" height="729" alt="Screenshot 2026-01-18 192321" src="https://github.com/user-attachments/assets/07a03d97-e310-4786-a2eb-6b544508ffb5" />


I configured a Wazuh SIEM to provide deep visibility into endpoint security through the integration of a rootcheck engine and kernel-level auditing. By analyzing the ingested event data, I successfully identified and categorized multiple host-based anomalies (Rule 510) and active policy enforcements via AppArmor denials (Rule 52002). The project demonstrated my ability to:

Reference: SIEM 7


<img width="1101" height="666" alt="Screenshot 2026-01-18 192745" src="https://github.com/user-attachments/assets/5075cb64-2798-449d-9e42-9ec32f0da12a" />

In this project, I configured Wazuh to perform deep-level auditing of an Ubuntu-Victim endpoint through host-based anomaly detection and kernel-level policy enforcement. By monitoring Rootcheck (Rule 510) and AppArmor (Rule 52002) events, I gained visibility into suspicious system behavior and unauthorized process attempts. I further mapped these activities to PCI DSS and GDPR compliance standards, demonstrating the ability to transform raw endpoint telemetry into professional, audit-ready security intelligence.

Reference: SIEM 8





<img width="799" height="673" alt="Screenshot 2026-01-18 201553" src="https://github.com/user-attachments/assets/1d9b062a-890e-4e4f-9985-df663eaf728e" />



I utilized Wazuh SIEM to perform deep-level auditing of an Ubuntu-Victim endpoint through host-based anomaly detection and kernel-level policy enforcement. By monitoring Rootcheck (Rule 510) and AppArmor (Rule 52002) events, I gained visibility into suspicious system behavior and unauthorized process attempts. I further mapped these activities to PCI DSS (10.6.1, 10.2.6) and GDPR compliance standards, demonstrating the ability to transform raw endpoint telemetry into professional, audit-ready security intelligence.



