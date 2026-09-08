# Corporate Campus Network — Cisco Packet Tracer

A Cisco Packet Tracer project that designs and simulates a multi-building corporate network with dynamic routing, automated IP address allocation, centralized DNS/HTTP services, and browser-based business process simulations.

## Project Overview

This project was developed for **CSE405 – Computer Networks** with the theme **“Data Communication in a Network.”**

The network represents a corporate campus consisting of five buildings:

- Headquarters
- Sales Office
- Tech Center
- Human Resources
- Finance Division

Each building has its own router and an internal LAN containing employee PCs and DHCP servers. The routers are interconnected using **OSPF (Open Shortest Path First)** to provide dynamic inter-building communication.

A centralized **DNS Server** and **Web Server** are deployed at the Headquarters. The web server hosts the domain:

`http://www.campusnet.com`

The project also demonstrates practical corporate workflows through browser-based mock interfaces for:

- Employee onboarding
- Company asset management
- Invoice processing

## Objectives

The main objectives of the project are to:

1. Design a scalable corporate network connecting multiple buildings.
2. Apply Class A IP addressing with appropriate subnetting.
3. Configure DHCP for automated IP address assignment.
4. Implement OSPF for dynamic routing between departmental networks.
5. Deploy centralized DNS and HTTP services at Headquarters.
6. Make the corporate website accessible from different buildings.
7. Simulate basic business processes through locally hosted web pages.
8. Verify end-to-end connectivity between different departmental networks.

## Network Architecture

The topology follows a distributed corporate-campus model where each building operates as a separate network segment connected through its dedicated router.

### Buildings and Network Segments

| Building | Network | Default Gateway |
|---|---|---|
| Headquarters | `10.0.0.0/8` | `10.0.0.254` |
| Sales Office | `20.0.0.0/8` | `20.0.0.254` |
| Tech Center | `30.0.0.0/8` | `30.0.0.254` |
| Human Resources | `40.0.0.0/8` | `40.0.0.254` |
| Finance Division | `50.0.0.0/8` | `50.0.0.254` |

Inter-router networks are also configured using Class A address ranges to establish communication between the different corporate locations.

> **Note:** The addressing table above summarizes the departmental LANs shown in the project topology. The actual Packet Tracer file remains the authoritative source for the complete interface-level addressing configuration.

## Key Technologies

### OSPF Routing

**OSPF** is used as the dynamic routing protocol between the five building routers.

This allows routers to dynamically learn remote networks and select suitable paths for inter-building communication instead of relying entirely on manually configured static routes.

### DHCP

DHCP is used to automatically provide client PCs with network configuration parameters, including:

- IP address
- Subnet mask
- Default gateway
- DNS server

The experimental results demonstrate successful DHCP requests from clients in multiple buildings.

### DNS

A dedicated DNS server is hosted at Headquarters with the address:

`10.0.0.1`

It is used to resolve the corporate domain:

`www.campusnet.com`

### HTTP / Web Server

A dedicated web server is hosted at Headquarters with the address:

`10.0.0.2`

The server provides the corporate web interface and hosts the simulated business-process pages.

## Simulated Corporate Services

The project goes beyond basic connectivity by demonstrating how network services can support common organizational activities.

### Employee Onboarding

A browser-based onboarding interface allows basic employee information such as name and department to be entered.

Example endpoint:

`http://www.campusnet.com/onboarding.html`

### Asset Management

An internal asset page demonstrates basic company asset information, including examples such as:

- Router
- Switch
- Printer

Example endpoint:

`http://www.campusnet.com/assets.html`

### Invoice Processing

An invoice-entry interface demonstrates basic invoice information handling using client name and amount fields.

Example endpoint:

`http://www.campusnet.com/invoice.html`

These pages are intended as **simulation/mock interfaces** for demonstrating network-enabled corporate processes rather than production business applications.

## Network Validation

The implementation was tested using several Packet Tracer verification scenarios.

### DHCP Verification

Successful DHCP requests were demonstrated from clients in:

- Headquarters
- Sales Office
- Human Resources

The clients received valid IP configuration automatically from their respective DHCP services.

### DNS and Web Access

The corporate domain `www.campusnet.com` was successfully accessed through the Packet Tracer web browser from:

- Headquarters
- Finance Division

This demonstrates that the centralized DNS and web services are reachable across the routed network.

### Inter-Building Connectivity

An end-to-end ping test from a **Tech Center PC** to a **Finance Division PC** was successful, confirming communication between different departmental networks through the routed infrastructure.

## Project Components

The Packet Tracer topology contains:

- 5 departmental routers
- Multiple switches
- 3 employee/client PCs per building
- DHCP servers for automated address allocation
- Dedicated Headquarters DNS server
- Dedicated Headquarters Web server
- Inter-router links
- OSPF-based dynamic routing
- Browser-based corporate service pages

## Repository Contents

A typical repository structure can be organized as follows:

```text
.
├── project.pkt
├── README.md
├── Project_Report.pdf
└── screenshots/
    ├── network-topology.png
    ├── dhcp-verification.png
    ├── web-access.png
    ├── business-processes.png
    └── connectivity-test.png
```

If the report or screenshots are stored under different filenames/directories in the repository, update the paths above accordingly.

## How to Run the Project

### Requirements

- **Cisco Packet Tracer**
- The provided `.pkt` project file

### Steps

1. Clone or download this repository.
2. Open `project.pkt` using Cisco Packet Tracer.
3. Allow the topology to load completely.
4. Inspect the five departmental networks and router interconnections.
5. Use the PC **Desktop → IP Configuration** interface to verify DHCP assignment.
6. Open the **Web Browser** from a client PC.
7. Access:

   `http://www.campusnet.com`

8. Test the business-process pages:
   - `/onboarding.html`
   - `/assets.html`
   - `/invoice.html`
9. Use the Packet Tracer command prompt to perform inter-building ping tests.

## Expected Results

After the network is configured correctly:

- Client PCs should receive IP addresses through DHCP.
- Routers should exchange routing information using OSPF.
- Different departmental networks should communicate with one another.
- `www.campusnet.com` should resolve through the centralized DNS server.
- The corporate web server should be accessible from other buildings.
- The simulated onboarding, asset management, and invoice pages should be reachable through the internal website.
- Inter-building ping tests should complete successfully.

## Project Outcome

The simulation demonstrates a functional corporate network that combines **network connectivity, dynamic routing, automated IP management, centralized services, and application-level access**.

The successful DHCP, DNS/HTTP access, and cross-building connectivity tests show that the designed infrastructure can support communication and basic service delivery across the five-building corporate environment.

## Academic Context

**Course:** CSE405 – Computer Networks  
**Project Topic:** Data Communication in a Network  
**Platform:** Cisco Packet Tracer  
**Routing Protocol:** OSPF  
**Addressing:** Class A IPv4 addressing  
**Core Services:** DHCP, DNS, HTTP

## Disclaimer

This project is an academic network simulation created in Cisco Packet Tracer. The business-process interfaces are simplified mockups intended for demonstration and educational purposes and are not production-ready enterprise applications.
