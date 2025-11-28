# DMVPN with IPsec Lab (EVE-NG)

This lab simulates a secure enterprise network using **DMVPN Phase 2** with **IPsec encryption** and **EIGRP dynamic routing** across a Head Quarter and three Branches, connected via a simulated Internet cloud in **EVE-NG**.

## 🧩 Topology Overview

## 📷 Topology Diagram

Refer to `topology.png` for a visual overview of the lab setup.

- **HQ Router**  
  - LAN: `10.0.1.0/24`  
  - Public IP: `192.168.81.222`

- **Branch Routers**  
  - BR1: `10.0.2.0/24` — Public IP: `192.168.81.134`  
  - BR2: `10.0.3.0/24` — Public IP: `192.168.81.138`  
  - BR3: `10.0.4.0/24` — Public IP: `192.168.81.137`

- **Tunnel Interface Subnet**: `172.16.0.0/24`  
- **Routing Protocol**: EIGRP  
- **Internet Simulation**: Management Cloud

## 🔐 VPN Configuration

- **DMVPN Phase 3** with IPsec encryption
- **ISAKMP Phase 1**: Policy and key exchange
- **IPsec Phase 2**: Transform set and profile applied to tunnel interfaces
- **Default routes** configured for Internet access

## 🖥️ End-to-End Test

- Two **Windows 7 machines** deployed in different LANs
- **Folder sharing** successfully tested between them

## 🖥️ Internet Connectivity Test
- From the **Windows 7 machine** I could access **cisco.com** website through the browser  

## 🛠️ Setup Steps

1. Import `DMVPN-with-IPsec-Lab.unl` into EVE-NG
2. Apply configurations from `HQ.txt`, `BR1.txt`, `BR2.txt`, `BR3.txt`
3. Verify tunnel establishment and routing

## 🔍 Validation Commands

- Tunnel status:  
  `show ip interface brief`  
  `show dmvpn`

- IPsec status:  
  `show crypto isakmp sa`  
  `show crypto ipsec sa`

- Routing:  
  `show ip route eigrp`  
  `show ip eigrp neighbors`

- Connectivity:  
  `ping <remote LAN IP>`  
  `traceroute <remote LAN IP>`


## 📌 Notes

- Ensure NHRP is properly configured on all routers
- IPsec profiles must match across peers
- EIGRP should advertise tunnel and LAN networks

---

**Author**: Mohamed Gowaied  
**Platform**: EVE-NG  
**Tags**: #DMVPN #IPsec #EIGRP #Cisco #NetworkLab #EVENG #VPN #Routing #Security
