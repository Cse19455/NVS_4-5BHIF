## NAT
Nat übersetzt private adressen in öffentliche Adressen.
War zu Zeiten von Ipv4 notwendig da der Adressbereich von Ipv4 zu klein war um Hosts automatisch global unique Adressen zuzuweisen.

**NAT Router** - Router der NAT translation betreiben kann


**Inside** = Adresse die zu übersetzen ist
**Outside** = Destination Adresse

**Global** = Global Adress 
**Local** =  Local Adress (in "private" Network)

## Static NAT (1:1)
useful for devices that need to have a consistent adress ! *(zB. Webserver...)*

#### Configuration :
(config-if)# ip nat inside (zu übersetzende adresse)
(config-if)# ip nat outside (zu benutzende globale adresse)

## Dynamic NAT (1:n)
uses a pool of adresses and dynamicly assigns them on the first come first serve basis. 
*(**Attention!** enough public adresses are required)*

#### Configuration :
1) Define global adress pool
	- ip nat pool (name) (from) (to) netmask (subnet mask)
2) create access list and permit all inside local adresses
	- access-list (number) permit (adress + wildcard)
3) Bind the ACL to the nat Pool
	- ip nat inside source list (number) pool (name )   
4) Identify Inside and outside interfaces
	- ip nat inside / outside
## PAT (NAT overload)
maps multiple private adresses to one global adress
*(TCP port number of the client is used for identification)*

Always assigns next available port number
(ICMP has no port number  -> uses Query ID instead)

### Configuration
Same as Dynamic nat + add "overload" keyword to the binding command
=> ip nat inside source list (number) pool (name) overload

## NAT64
Translate ipv4 to ipv6 addresses and vice versa

### Show - Commands
Show ip nat translations (verbose)
Show ip nat statistics