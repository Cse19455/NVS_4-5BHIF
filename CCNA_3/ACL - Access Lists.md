
### Standart ACL
	nur source
	(Layer 3)
### extended ACL
	source und destination ports und Ip
	(Layer 3 + Layer 4)

### Standart numbered ACL
	normalerweise beim ziel outgoing

access list 100 permit UDP any {ip} {wildcard mask} eq {Port}

 ```
 ip access-group VLAN10_IN in
 ip access-group VLAN10_OUT out
```


### IPv6
[only named Extended]

```
R1(config)# ipv6 access-list NO_TELNET

R1(config-ipv6-acl)# permit tcp host 2001:db8:FC31e:1::1 any eq 23

R1(config-ipv6-acl)# exit
```

## Wildcard Mask
Inverse Mask
0 - Bit must be the same
1 - Bit must not be the same
=> is used to specify a range of IP adresses 

Bsp.
**10.0.1.0** 0.0.0.255 [Wildcard]
=> Every Ip from 10.0.1.0 - 10.0.1.255 can be used
*(Remember Ip's 0 & 255 are special cases)*


## Short Summary

	Standart Named ACL (access-list 1 permit ...)
	Standart Numbered ACL (ip access-list "name" permit ...)
	Extended Named ACL (ip access-list "name" tcp any any eq port )
	Extended Numbered ACL (ip access-list 1 tcp any any eq port)
	
-- use **established** Keyword for specification that requests outside the network are not forwarded (ACK - Flag must be 1)
