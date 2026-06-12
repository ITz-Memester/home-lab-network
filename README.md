🖥️ Cybersecurity Home Lab

A virtualized enterprise-style network built to simulate a real corporate environment — including Active Directory, VLANs, DNS, DHCP, Docker, and firewall configuration — all running locally using VirtualBox.


🗺️ Network Diagram

...




⚙️ Lab Overview

VMOSRoleRouter/FirewallpfSenseInter-VLAN routing, DHCP relay, firewall rulesDomain ControllerWindows Server 2022Active Directory, DNS, DHCPWorkstationWindows 10/11Domain-joined client machineLinux ServerUbuntuDocker host, containerized servicesAttacker MachineKali LinuxNetwork scanning, firewall testing


🔧 What I Built


Virtual Network — Multiple VMs networked together using VirtualBox internal networking, simulating a real office LAN
VLAN Segmentation — Separated traffic into Management, Workstation, and DMZ VLANs with dedicated subnets (192.168.10.0/24, etc.)
pfSense Firewall — Configured inter-VLAN routing, firewall rules, and DHCP relay so VMs can communicate where allowed
Active Directory — Set up a Windows Server 2022 domain controller with users, groups, and Group Policy
DNS & DHCP — Internal DNS resolves hostnames like dc.corp.local; DHCP automatically assigns IPs to clients
Docker on Ubuntu — Deployed containerized services (nginx web server) on the Linux VM inside the DMZ
Kali Penetration Testing — Used nmap to scan the network, tested firewall rules, and verified what was and wasn't exposed



🛠️ Technologies Used

Show Image
Show Image
Show Image
Show Image
Show Image
Show Image


📁 Repository Structure

home-lab-network/
├── README.md
├── network-diagram/       # Visual topology map
├── pfSense/               # Firewall config notes + screenshots
├── windows-server/        # AD, DNS, DHCP setup walkthrough
├── docker/                # Container deployments
├── kali-testing/          # Scan results, firewall tests
└── lessons-learned/       # Issues encountered and how I fixed them


🚧 Challenges & What I Learned


Inter-VLAN routing was the hardest part to get right — pfSense needed specific firewall rules on each interface before traffic would pass between VLANs
DNS misconfiguration initially broke domain join — learned how critical proper DNS pointing is for Active Directory
Docker networking on a segmented network required understanding bridge vs. host networking modes
Overall this gave me a much deeper understanding of how enterprise networks actually function day-to-day



📸 Screenshots

...




🎯 Purpose

Built this lab to develop hands-on skills relevant to roles in SOC analysis, network administration, and systems administration. Everything here reflects real tools used in enterprise environments.
