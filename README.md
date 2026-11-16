🔐 Secure Smart Home Network

Network Engineering & Cybersecurity Project

📌 Project Overview

This project demonstrates the design, implementation, and security configuration of a segmented smart home network using Cisco Packet Tracer 8.2.2.

The objective was to build a functional network that supports multiple departments and device categories while implementing security controls to reduce unauthorized network access.

The project covers VLAN segmentation, inter-VLAN routing, DHCP, NAT/PAT, access control lists, secure remote administration, and Layer 2 switch security.

Project Objectives

Design a structured network topology.

Separate devices using VLANs.

Enable inter-VLAN routing.

Configure automatic IP address assignment using DHCP.

Establish connectivity to a simulated internet server.

Implement NAT/PAT.

Restrict unauthorized network communication using extended ACLs.

Secure router administration using SSH.

Implement switch port security.

Configure DHCP Snooping.

Verify network connectivity and security policies.

🛠️ Technologies and Tools

Technology                       Purpose

Cisco Packet Tracer 8.2.2        Network simulation
Cisco 2911 Routers               Routing and NAT/PAT
Cisco 2960 Switches              VLANs and Layer 2 security
IEEE 802.1Q                      VLAN trunking
DHCP                             Automatic IP assignment
Extended ACLs                    Network traffic filtering
SSH                              Secure remote administration
Port Security                    MAC address restrictions
DHCP Snooping                  Protection against unauthorized DHCP servers

🌐 Network Architecture

The network contains:

2 Cisco routers: R1-EDGE and R2-ISP

3 Cisco switches: SW1-CORE, SW2-HOME, and SW3-OFFICE

Home computers

Office computers

Guest and IoT test computers

A private server

A simulated internet server

VLAN and IP Addressing Plan

VLAN ID     VLAN Name      Network Address      Default Gateway
10          HOME           192.168.10.0/24      192.168.10.1

20          OFFICE         192.168.20.0/24      192.168.20.1

30           IOT           192.168.30.0/24      192.168.30.1

40          GUEST          192.168.40.0/24      192.168.40.1

50          SERVERS        192.168.50.0/24      192.168.50.1

99         MANAGEMENT      192.168.99.0/24      192.168.99.1

🔧 Network Implementation

1. VLAN Configuration

Six VLANs were created to separate different categories of devices.

This provides logical segmentation and reduces unnecessary broadcast traffic between network groups.

2. Inter-VLAN Routing

Router-on-a-stick was implemented on R1-EDGE using IEEE 802.1Q subinterfaces.

Each VLAN was assigned a dedicated default gateway.

3. DHCP Configuration

DHCP pools were configured on R1-EDGE to provide automatic IP addressing for the HOME, OFFICE, IOT, and GUEST networks.

DHCP was initially verified, although an issue affecting PC-OFFICE1 was encountered during later security configuration.

4. Static Routing and NAT/PAT

A simulated ISP connection was established between R1-EDGE and R2-ISP.

NAT/PAT was configured to translate internal private IP addresses for communication with the simulated external network.

5. Extended Access Control Lists

Extended ACLs were implemented to restrict traffic originating from Guest and IoT networks.

Security policies included:

Blocking Guest access to Home and Office networks.

Blocking Guest access to the private server.

Blocking IoT access to Home and Office networks.

Restricting Office access to the Management VLAN.

Allowing permitted access to the simulated internet.

6. SSH Configuration

SSH version 2 was configured on the routers to support encrypted remote administration.

Local username authentication was implemented, and Telnet access was disabled on the configured VTY lines.

7. Switch Port Security

Port security was configured on selected access ports.

The configuration included:

Maximum of one secure MAC address per port.

Sticky MAC address learning.

Restrict violation mode.

8. DHCP Snooping

DHCP Snooping was configured on the switches.

Router-facing and appropriate upstream interfaces were configured as trusted, while client-facing interfaces remained untrusted.

The feature was configured successfully, but its complete operational effectiveness was not verified.

🧪 Testing and Verification

Test                    Result
VLAN configuration       Passed

802.1Q trunking          Passed

Inter-VLAN routing       Passed

Simulated internet connectivity    Passed

NAT/PAT connectivity      Passed

Guest ACL restrictions     Passed

IoT ACL restrictions      Passed

SSH remote login         Passed

Port security           Passed

DHCP Snooping configuration       Verified

PC-OFFICE1 DHCP after security changes      Unresolved

📸 Project Screenshots

Network Topology
VLAN Configuration
Trunk Configuration
Routing Table
DHCP Bindings
NAT/PAT
ACL Security
SSH Configuration
Switch Port Security
Internet Connectivity
Guest Network Isolation

⚠️ Known Issues and Limitations

During DHCP Snooping configuration, PC-OFFICE1 stopped receiving an IP address automatically and was assigned an APIPA address.

Static IP testing confirmed that the computer could communicate with its VLAN gateway, indicating that basic VLAN connectivity remained operational.

The DHCP issue requires further troubleshooting.

Additional limitations:

ACLs provide selected source-based restrictions rather than complete bidirectional isolation.

DHCP Snooping was configured but not fully validated against a rogue DHCP server.

BPDU Guard and unused-port hardening were not completed.

The internet connection is simulated using a Packet Tracer server.

📚 Skills Demonstrated

Network Engineering

Network topology design

VLAN segmentation

Inter-VLAN routing

DHCP configuration

Static routing

NAT/PAT

Network troubleshooting

Cybersecurity

Network access control

ACL implementation

SSH configuration

Switch port security

DHCP Snooping configuration

Network segmentation

Security testing

🚀 Future Improvements

Resolve the remaining DHCP issue.

Implement BPDU Guard.

Disable unused switch ports.

Restrict SSH access to authorized management hosts.

Improve bidirectional network isolation.

Add wireless network security.

Introduce centralized logging and monitoring.

📂 Project Files

The repository contains:

Secure_Smart_Home_Network.pkt — Cisco Packet Tracer project file.

screenshots/ — Network configuration and testing evidence.

README.md — Project documentation.

📄 Conclusion

This project demonstrates practical network engineering and cybersecurity skills through the design, implementation, and testing of a segmented network.

It provided hands-on experience with Cisco networking technologies, access control, device hardening, and troubleshooting.

The project also highlights the importance of validating security controls and documenting unresolved technical issues.