
# Lab 1 – Basic Firewall Ruleset

## Objective
Configure the Phoenix Contact mGuard 1105 firewall to block all traffic by default and allow **only SSH** from WAN → LAN.

## Topology
- Laptop (WAN): 172.20.200.2/24
- mGuard WAN: 172.20.200.1/24
- mGuard LAN: 192.168.1.1/24
- Raspberry Pi: 192.168.1.101/24

[Laptop: 172.20.200.2] ---> [mGuard 1105: 172.20.200.1] ---> [Switch] ---> [Raspberry Pi: 192.168.1.101]

## Steps
1) Set firewall policy to default deny
2) Created port forwarding rule:
	- Protocol: TCP
	- Incoming Port: 22
	- To IP: 192.168.1.101
	- To port 22
3) Saved and applied config

## Testing
- Ping Test:
'''bash
ping 192.168.1.101
'''
-> Failed (expected)

- SSH Test:
'''bash
ssh ryorgason@172.20.200.1
'''
-> Successful
