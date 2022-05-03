#### DHCP 

Manually configuring Host
Slaac or Slaac + DHCPv6 Server
stateful DHCPv6 Server

**Stateless** -> no one keeps track of the addresses

Discover
Offer
Request 
Acknoledge
...

#### SLAAC
relies on Neighbour Discovery Protocol
other Router in network will reply with RA messages
	- prefix length
	- def. gateway
=> with this inf. it will create a global unique adress using EUI-64