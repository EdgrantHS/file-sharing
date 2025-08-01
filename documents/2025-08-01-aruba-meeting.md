## Aruba Meeting with Dr. Gde

> Date: 2025-08-01  
> Recording: [YouTube Link | Meeting in Indonesian](https://youtu.be/IHW1nLBgioY?si=WIm3-SxZqE-RzW3X)

## Table of Contents

- [Aruba Meeting with Dr. Gde](#aruba-meeting-with-dr-gde)
- [Table of Contents](#table-of-contents)
- [Meeting Minutes](#meeting-minutes)
  - [Attendees](#attendees)
  - [Main Agenda \& Objectives](#main-agenda--objectives)
  - [Key Discussions \& Updates](#key-discussions--updates)
  - [Action Items](#action-items)
  - [Conclusion](#conclusion)
- [Meeting Summary](#meeting-summary)
  - [Meeting Agenda and Goals](#meeting-agenda-and-goals)
  - [O-RAN Integration](#o-ran-integration)
  - [Required Access and Challenges](#required-access-and-challenges)
  - [Technical Implementation and Tutorial (Fajri's Experience)](#technical-implementation-and-tutorial-fajris-experience)
  - [Modern Coding Trends and Documentation](#modern-coding-trends-and-documentation)
  - [Data Scope and Future Development](#data-scope-and-future-development)
  - [Team Collaboration and Support](#team-collaboration-and-support)

## Meeting Minutes

> AI Generated based on the meeting transcript, then reviewed and edited manually for accuracy.

### Attendees

- Dr. Gde
- Ian (NTUST, S3 Student)
- Fajri (UI, Recently Completed Thesis)
- Joshevan (UI Alumni, S2 Student at NTUST)
- Edgran (UI Student)
- Stefanus (UI Student)
- Fauzan (UI Student)

### Main Agenda & Objectives

- The primary agenda was the **transfer of knowledge regarding WiFi crawling** from Fajri, who successfully installed the system and started collecting data.
- The immediate goal for Joshevan, Edgran, Stefanus, and Fauzan is to **replicate Fajri's setup** to begin collecting data themselves.
- The long-term objective is to develop an **effective WiFi monitoring system** and an **energy monitoring system**. This aims to create a dashboard capable of **automatically controlling WiFi energy usage**, deciding when to disable, sleep, or wake up WiFi access points.

### Key Discussions & Updates

- Covered in the [meeting summary](#meeting-summary)

### Action Items

- Stefanus, and Fauzan are to **replicate Fajri's WiFi crawling setup**
- Joshevan, Edgrant **Verify the Aruba Crawler** and ensure it works with the UI environment.
- Fauzan and Stefan are to **provide their SSO accounts** to Dr. Gede so he can register them for VPN access to UI's DSTI.
- Stefan and Fauzan are to **test Joshevan's updated crawler** for wider campus data collection once Fajri's setup is replicated.
- Fajri is to **share the hyperlink** to his GitHub repository with the group. _(Already completed as of writing this report)_
- All relevant team members are to **join the designated WhatsApp group** for communication and sharing updates.
- New students are to focus on **literature study** and defining problem statements for their seminars.

---

## Meeting Summary

### Meeting Agenda and Goals

- The primary agenda for the meeting was the **transfer of knowledge regarding WiFi crawling** from Fajri, who successfully installed the system and started collecting data.
  - The immediate goal for Joshevan, Edgrant, Stefanus, and Fauzan is to replicate Fajri's setup to begin collecting data themselves.
  - The long-term goal is to develop an **effective WiFi monitoring system** and **energy monitoring system**.
- The aim is to create a dashboard capable of **automatically controlling WiFi energy usage**, deciding when to disable, sleep, or wake up WiFi access points.

### O-RAN Integration

- The project extends beyond just WiFi platforms to include O-RAN standards, which encompass cellular networks.
  - The collected WiFi data parameters will be converted to the 3GPP standard, which is typically used for cellular parameters, because the main platform is cellular-based.
  - Both WiFi and cellular systems share similar concepts, differing mainly in naming conventions.
  - There's potential to collaborate with Pak Ruki to develop a **private 5G testbed at FT UI**.
- NTUST can offer data processing services (server, GPU) to UI and ITB if they lack the necessary equipment, facilitating remote data processing.

### Required Access and Challenges

- To collect data, access is needed for **Aruba WiFi controllers**, **POE switches**, and **floor plans**.
  - Fajri has successfully accessed the dashboard and controller.
  - A significant challenge for external access to UI systems is the **Single Sign-On (SSO)** system for VPN access, as UI traditionally does not create SSO accounts for external parties.
  - A temporary solution allows Taiwan (NTUST) users to use the SSO accounts of UI students (like Edgrant and Joshevan) to access the VPN.
- Data shared should be processed only at Ian's location (NTUST) and not shared further, with private data like MAC addresses and student IDs being hashed.

### Technical Implementation and Tutorial (Fajri's Experience)

- Fajri successfully developed a WiFi adapter based on NTUST's code for UI's environment.
  - The setup involves a **Virtual Machine (VM)** running the WiFi crawler, accessible via **VS Code's Remote Explorer** and **Remote SSH**.
  - Users need **OpenVPN** to connect to the VM.
  - The VM connects to **Aruba WiFi controllers** and **POE switches** to pull configuration and status data (e.g., WiFi parameters, interface, power).
  - **InfluxDB** is used to store the crawled data in real-time, and **Grafana** is used for dashboarding and profiling of parameters.
  - Fajri used **XGBoost** for predictive analysis, specifically predicting total power based on active clients (users).
- The initial data collection scope was limited to **Gedung S** due to experimental nature and concerns about affecting overall UI network performance.

### Modern Coding Trends and Documentation

- The current trend in coding emphasizes defining project specifications in detail rather than extensive manual coding, using **AI tools like Copilot**.
  - These AI tools can generate code based on comprehensive specifications, including:
    1. **Use Case Diagram**: Defines project features and client needs.
    2. **System Architecture**: Outlines system components (e.g., WiFi controller, POE switch).
    3. **Message Sequence Chart (MSC)**: Details communication between components.
    4. **Class Diagram**: Defines objects, parameters, functions, and relationships (one-to-one, one-to-many).
  - **Thorough documentation** (e.g., using Markdown with Mermaid for diagrams) is crucial for efficient project handover and collaboration, especially for new students joining the project.
- Joshevan is also developing documentation for his updated WiFi adapter, including architecture, installation tutorials, and repository structure.

### Data Scope and Future Development

- Joshevan's updated WiFi adapter may be able to collect data from the entire UI campus if granted wider read access, which would not affect performance as it's read-only. This wider scope will be tested by Fauzan and Stefan.
  - NTUST plans to provide VPN access to UI to allow the crawled data to be pushed automatically to NTUST's Service Management and Orchestration (SMO) system, which will connect to AI models.
  - Potential future use cases for the collected data include:
    - **Energy saving** analysis (current power consumption often remains maximum regardless of network load, indicating waste).
    - Analyzing network utilization, throughput, attached users (stations), and WiFi controller CPU load.
    - Investigating **signal strength (RSSI)**.
    - Optimizing WiFi deployment based on user density and quality issues (e.g., slow WiFi in specific areas).
    - Developing more intuitive and informative dashboards for administrators.
    - Comparing different algorithms for more accurate results.

### Team Collaboration and Support

- Fajri will continue to support Stefanus and Fauzan with the implementation and troubleshooting of the existing setup.
  - Joshevan's updated crawler will also be tested.
  - Regular communication and sharing of issues/discoveries within a group chat and on GitHub are encouraged.
  - The UI team aims for a "research-first" approach for thesis work, directly translating research and documentation into their thesis structure, potentially using Overleaf.
