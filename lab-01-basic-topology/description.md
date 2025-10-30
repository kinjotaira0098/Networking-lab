# Lab 01: Inter-VLAN Routing + DHCP + ACL (RoAS)

**Goal:** Use a single router interface with 802.1Q subinterfaces to route between VLANs 10/20/30 and MGMT 99. Provide DHCP per VLAN and restrict access to the server VLAN (VLAN 99) with an inbound ACL.

**Topology (conceptual):**
PCs (VLAN 10/20/30) — Switch —(trunk)→ Router G0/0.{10,20,30,99}

**Key Configs:**
- G0/0 subifs: 10, 20, 30, 99 with gateway IPs
- DHCP pools: SALES/HR/IT/MGMT
- ACL `FILTER_SERVERS` applied inbound on G0/0.99
