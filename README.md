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

<a href="https://ibb.co/VqgTL6y"><img src="https://i.ibb.co/JsvHcZL/Screenshot-2024-06-19-170909.png" alt="Screenshot-2024-06-19-170909" border="0"></a>

Step 9: With the data from the Kali VM now forwarded to the SIEM, we can begin querying and analyzing the logs. In your Elastic Deployment, click the menu icon at the top left (three horizontal lines), then select the 'Logs' tab under 'Observability' to view the logs from the Kali VM.

<a href="https://ibb.co/MNWc8rF"><img src="https://i.ibb.co/4N98szh/screenshot9.png" alt="screenshot9" border="0"></a>

Step 10: In the search bar, enter a search query to filter the logs. For example, to find all logs related to Nmap scans, use the query: `event.action: "nmap_scan" OR process.args: "sudo"`. Click the "Search" button to execute the query. The search results will appear in the table below, and you can click on the three dots next to each event for more details.

<a href="https://ibb.co/26pKhzq"><img src="https://i.ibb.co/z5tfx3s/screenshot10.png" alt="screenshot10" border="0"></a>

<a href="https://ibb.co/Lz4jm3X"><img src="https://i.ibb.co/kgYbjts/Screenshot-19-6-2024-19448-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-19-6-2024-19448-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>

Step 11: To create a dashboard in the Elastic web portal:

1. Navigate to the Elastic web portal at https://cloud.elastic.co/.
2. Click on the menu icon at the top-left.
3. Under "Analytics," click on "Dashboards.

<a href="https://imgbb.com/"><img src="https://i.ibb.co/3Wb4Nx5/screenshot11.png" alt="screenshot11" border="0"></a>

Step 12:

4. Click the “Create dashboard” button at the top-right to start a new dashboard.

5. Press “Create Visualization” to add a new visualization to the dashboard.

6. Choose between “Area” or “Line” as your visualization type to create a chart displaying event counts over time.

7. In the visualization editor under the "Metrics" section on the right:

Select "Count" as the vertical field type.
Choose "Timestamp" for the horizontal field.
This setup will display the count of events over time in your visualization.
Click on the "Save" button to save the visualization. Complete any remaining settings or configurations as needed to finalize your dashboard setup.

Step 13: To access the Alerts section in Elastic Security:

Click on the menu icon at the top-left.
Under "Security," click on "Alerts."
Click on "Manage rules" located at the top right corner of the page.

<a href="https://ibb.co/z7yZXbY"><img src="https://i.ibb.co/MGY7cp4/screenshot13.png" alt="screenshot13" border="0"></a>

Step 14:

To create a new rule for detecting Nmap scan events:

1. Click on the "Create new rule" button at the top right.
2. Under the "Define rule" section, select the "Custom query" option from the dropdown menu.
3. In the "Custom query" field, set the conditions using the following query to detect Nmap scan events:

```
event.action: "nmap_scan"
```

This query will filter events where the action is "nmap_scan". Adjust the query as needed to match specific criteria for detecting Nmap scans or other security events.

<a href="https://ibb.co/McfHtBp"><img src="https://i.ibb.co/T41G7WR/Screenshot-19-6-2024-19376-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-19-6-2024-19376-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>

Step 15: 

After setting the custom query to match events with the action "nmap_scan," click "Continue." In the "About rule" section, give your rule a name (e.g., Nmap Scan Detection) and a description. Set the severity level for the alert to prioritize alerts based on their importance. Keep the default settings under "Schedule rule" unchanged, and then proceed by clicking "Continue."

<a href="https://ibb.co/VQ0Zg7X"><img src="https://i.ibb.co/3M5qpDt/screenshot15.png" alt="screenshot15" border="0"></a>

Step 16:

In the "Actions" section, choose the action you want triggered when the rule detects an event. Options include sending an email notification, creating a Slack message, or triggering a custom webhook. Finally, click the "Create and enable rule" button to create the alert with your selected actions.


<a href="https://ibb.co/Zdtgg6k"><img src="https://i.ibb.co/tBk22MW/screenshot16.png" alt="screenshot16" border="0"></a>

Step 17:
Once the alert is created, it will monitor your logs for Nmap scan events. When an Nmap scan event is detected, the alert will trigger and execute the selected action. You can manage and view all your alerts in the "Alerts" section under "Security."

<a href="https://ibb.co/YNSC5ps"><img src="https://i.ibb.co/yNC9zWj/Screenshot-19-6-2024-193037-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-19-6-2024-193037-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>

<a href="https://ibb.co/QnVdsmy"><img src="https://i.ibb.co/K7gwCyT/Screenshot-19-6-2024-195832-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-19-6-2024-195832-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>

<a href="https://ibb.co/XzhKtVz"><img src="https://i.ibb.co/7GwZKbG/Screenshot-19-6-2024-20154-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-19-6-2024-20154-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>

<a href="https://ibb.co/2MGpBc3"><img src="https://i.ibb.co/1XF4xRG/Screenshot-25-6-2024-204531-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io.jpg" alt="Screenshot-25-6-2024-204531-d1c72ef5ac404316a494844cbdbdde8b-us-central1-gcp-cloud-es-io" border="0"></a>














