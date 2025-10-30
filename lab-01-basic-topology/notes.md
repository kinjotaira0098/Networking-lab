# Notes

- Router-on-a-stick works only if the physical link (G0/0) is UP and the switch port is a TRUNK carrying VLANs 10/20/30/99.
- DHCP handed out default gateways matching subinterface IPs (.1 in each VLAN).
- ACL `FILTER_SERVERS` is INBOUND on G0/0.99, so it filters traffic **entering** the router from VLAN 99 toward other VLANs. Revisit placement if your intent was to filter *into* VLAN 99 from user VLANs (then apply on those subinterfaces instead).

## Verification Commands
Router# show ip interface brief
Router# show ip dhcp binding
Router# show access-lists FILTER_SERVERS
Router# show running-config interface g0/0.10
Router# ping 192.168.99.10
Router# traceroute 192.168.99.10

