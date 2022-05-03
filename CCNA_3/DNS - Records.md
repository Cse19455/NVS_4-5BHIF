#### A-Record
Domainname to ipv4

#### AAAA-Record (Quad-A)
Domainname to ipv6

#### CNAME-Record
Zeigt Aliase eines Domain names

#### MX-Record
**Mail-Exchange-Record**
Mail Server -> gegebenem Domain name

#### PTR-Record
*Reverse-Lookup*
Ip adress -> Hostname

```
42.2.0.192.in-addr.arpa. 3600 IN  PTR  example.com.

1.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.8.b.d.0.1.0.0.2.ip6.arpa. 3600 IN PTR test-ipv6.example.com.
```

#### NS-Record
Zonenbestimmung (Zuständigkeit)

#### Usage
nslookup
set q=(record)
(Domain)