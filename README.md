# Elastic-SIEM-Lab
# PROJECTNAME

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Elastic Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis via nmap by using Kali Linux Virtual Box (VM) for capturing network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
Step 1: Log in to your Elastic SIEM instance. Navigate to the Integrations page by clicking on the Kibana main menu at the top left and selecting 'Integrations' from the bottom of the list.

<a href="https://ibb.co/D94bqQz"><img src="https://i.ibb.co/ZBdJZxG/screenshot.png" alt="screenshot" border="0"></a>

Step 2: Search for 'Elastic Defend' and click on it to open its integration page.

<a href="https://ibb.co/yFDZgM4"><img src="https://i.ibb.co/zV1BPL6/screenshot2.png" alt="screenshot2" border="0"></a>

Step 3: Click on 'Install Elastic Defend' and follow the instructions on the integration page to install the agent on your Kali VM.

<a href="https://ibb.co/MMf6syb"><img src="https://i.ibb.co/f49v2Vb/screenshot3.png" alt="screenshot3" border="0"></a>

Step 4: Ensure 'Linux' is selected on the page, then copy the provided command to your clipboard.

<a href="https://ibb.co/rcTxmqq"><img src="https://i.ibb.co/P93cNJJ/screenshot4.png" alt="screenshot4" border="0"></a>

Step 5: Paste the copied command into the terminal of your Kali VM. Run the command.

<a href="https://imgbb.com/"><img src="https://i.ibb.co/cJRhcCj/screenshot0.png" alt="screenshot0" border="0"></a>

Step 6: Once the agent is installed, which can take a few minutes, you will see a message stating 'Elastic Agent has been successfully installed.' The agent will automatically start collecting and forwarding logs to your Elastic SIEM instance, though it might take a few minutes for the logs to appear in the SIEM.

<a href="https://imgbb.com/"><img src="https://i.ibb.co/MByYnPQ/Screenshot-2024-06-19-165445.png" alt="Screenshot-2024-06-19-165445" border="0"></a>

Step 7: To verify the agent installation, run the following command: `sudo systemctl status elastic-agent.service`.

<a href="https://ibb.co/9hcMZ77"><img src="https://i.ibb.co/ypd34rr/Screenshot-2024-06-19-165714.png" alt="Screenshot-2024-06-19-165714" border="0"></a>

Step 8: In this exercise, I used the Nmap tool (Network Mapper), a free and open-source utility for network exploration, management, and security auditing. Nmap is designed to discover hosts and services on a computer network, effectively creating a network 'map.' It can scan hosts for open ports, identify the operating system and software running on the target system, and collect additional network information. Running Nmap scans generates several security events, including the detection of open ports and the identification of services on those ports. Perform a few more Nmap scans using commands like `nmap -sS <localhost>`, `nmap -sT <localhost>`, and `nmap -p- <localhost>`etc.

<a href="https://ibb.co/hy98Rvk"><img src="https://i.ibb.co/7XCyJFH/Screenshot-2024-06-19-172403.png" alt="Screenshot-2024-06-19-172403" border="0"></a>

<a href="https://ibb.co/hy98Rvk"><img src="https://i.ibb.co/7XCyJFH/Screenshot-2024-06-19-172403.png" alt="Screenshot-2024-06-19-172403" border="0"></a>

