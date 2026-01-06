# Packet Tracer Network Simulation

## Project Overview

This project presents a **complete implementation** of a given Packet Tracer network scenario using **Cisco Packet Tracer Student Version 8.2.2+**. All requirements  have been **fully designed, configured, tested, and validated** through simulation.

The implementation demonstrates practical understanding of **VLSM subnetting, dynamic routing protocols, route redistribution, DHCP, NAT, and ACLs**.

---
## Topology Implemented
![Network Topology](topology.png)

---

## Tools & Environment

* **Cisco Packet Tracer**: Student Version 8.2.2 or above
* **Routing Devices**: Cisco Routers & Switches (as per topology)
* **Configuration Method**: CLI-based manual configuration

---

## VLSM Subnetting (Implemented)

* Variable Length Subnet Masking (**VLSM**) is implemented across **all networks** in the topology.
* Subnetting is based on the **individual host requirements** provided the assigned *IP address* block.
* Networks are allocated **alphabetically**, as specified.
* Extra Networks were assigned from **vacant subnets** derived from the VLSM tree.
* CIDR notation was **adjusted where required** to accommodate large host requirements, with proper justification.

A **handwritten VLSM tree chart** has been prepared.

---

## Routing Protocol Configuration (Completed)

### First Row Routing

* **Block 1**: OSPF — Area 1
* **Block 2**: EIGRP — AS 11
* **Block 3**: RIP (Version 2)

### Second Row Routing

* **Block 1**: RIP (Version 2)
* **Last Block**: OSPF — Area 2

All routing domains were verified using routing tables and end-to-end connectivity tests.

---

## Route Redistribution (Completed)

Route redistribution has been correctly configured to ensure full network reachability:

* **Router 1**: Redistribution between OSPF (Area 1) and EIGRP (AS 11)
* **Router 2**: Redistribution between OSPF and RIP
* **Router 3**: Redistribution between EIGRP and RIP
* **Router 4**:

  * Redistribution between EIGRP and RIP
  * Redistribution between OSPF Area 1 and OSPF Area 2

Appropriate metrics were applied to prevent routing issues.

---

## DHCP Implementation (Verified)

Dynamic IP allocation has been implemented as follows:

* **DHCP 2 (Second Block)** provides IP addresses to:

  * All EIGRP networks (first row)
  * OSPF Area 1 networks
  * RIP networks (first row)

* **DHCP 1 (OSPF Area 2 Block)** provides IP addresses to:

  * OSPF Area 2 networks
  * RIP networks (second row)

All hosts successfully receive valid IP configurations via DHCP.

---

## NAT Configuration (Implemented)

* **NAT** is configured on **Router 10**
* NAT is applied to **Network G**
* The **private IP address range** provided in the IP address file is used

NAT functionality was verified through successful communication beyond the private network.

---

## Access Control Lists (ACLs) — Implemented & Tested

Extended ACLs were configured to enforce the following access restrictions:

1. One specific PC in **Network L** is blocked from accessing the **Web Server**
2. One specific PC in **Network E** is blocked from accessing the **Data Server** in the first block
3. All hosts in **Network A** are blocked from accessing the **TFTP Server**

The Web, Data, and TFTP servers are treated as hosts only; no services are enabled.

---

## Verification & Testing

* Connectivity tested using `ping` and `tracert`
* Routing tables verified on all routers
* DHCP bindings checked on DHCP servers
* NAT translations verified on Router 10
* ACL behavior validated by controlled access tests

All test cases produced the **expected results**.

---

## Files

* Packet Tracer Simulation File (`.pkt`)
* Handwritten VLSM Tree

Multiple backup copies of the `.pkt` file were maintained throughout development.

---
