# Networking

## Ping

* Mass ping: `nmap -sP 192.168.1.1-254`
	* <http://www.cyborgworkshop.org/2013/12/06/perform-a-ping-sweep-using-nmap/>
* Ping Range
	* <http://www.linuxscrew.com/2007/09/17/ping-range-of-ip-addresses-in-parallel-with-fping/>
		
		```
		sudo fping -s -g 192.168.0.1 192.168.0.9 -r 1

		That will output:
		
		192.168.0.1 is alive
		192.168.0.7 is alive
		192.168.0.2 is unreachable
		192.168.0.3 is unreachable
		192.168.0.4 is unreachable
		192.168.0.5 is unreachable
		192.168.0.6 is unreachable
		192.168.0.8 is unreachable
		192.168.0.9 is unreachable
		
		9 targets
		2 alive
		7 unreachable
		0 unknown addresses
		
		14 timeouts (waiting for response)
		16 ICMP Echos sent
		2 ICMP Echo Replies received
		0 other ICMP received
		
		0.05 ms (min round trip time)
		0.44 ms (avg round trip time)
		0.84 ms (max round trip time)
		2.183 sec (elapsed real time)
		```
		
	* In order to scan /24 network (254 hosts) and show only alive hosts the following command can be used:

		```
		sudo fping -a -q -g 192.168.0.0/24
		```

## Bad IPs/Black List tools
* <https://www.netmess.org/examine-your-attackers/>
* <https://www.netmess.org/wp-content/uploads/2013/09/key-ok.png>