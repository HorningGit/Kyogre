## Steps for Security Gateway -> (Netgate 1100 ~ pfSense)
- Configure pfSense port with IPv4 (ex. 192.168.2.1)
- Configured as DNS Server
- Configured as DHCP Server
- Create a NAT policy so that outgoing traffic to the Internet is NATed to the pfSense WAN IP. Automatic NAT rules may not work here. You may need to set it to Hybrid rules so you can configure this more precisely. You may need to manually create a NAT rule for the LAN/igb0 as well as that may become undone when switching to hybrid or manual mode.
- Due to the "all sources, all destinations, all protocols" type of rule you need to create to get wifi access to the Internet, it may also allow wireless to LAN access and the other way around so create the appropriate deny rules at the top of the list of firewall rules to stop that from happening.
- A floating rule (instead of rules on the igb0 and igb1 tabs) would address this because you can then specify which interfaces are involved, ie: all source from igb0 to all destinations only to re0. If you create floating rules, do not create rules on the LAN and Wireless tabs. Do one or the other.
- WAN to Bridge Mode
## Steps for Previous Home Router -> (Nighthawk AX5400)
- Configured for **AP MODE**
- Verify router isn't providing DHCP
- Connect LAN port to pfSense's configured port

## Steps for Managed Switch -> (Cisco SG250-08HP ~ Cisco IOS)

## Steps for Raspberry Pi -> (RPi4, RPi4, RPi3B+)

## Steps for Workstation -> Server


#### Useful Links
<p>https://setuprouter.com/router/netgear/nighthawk-x6-r8000/ip-address.htm</p>
