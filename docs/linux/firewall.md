# Linux Firewalls

## IPTables

* Limit connections: <http://unix.stackexchange.com/questions/139285/limit-max-connections-per-ip-address-and-new-connections-per-second-with-iptable>
	* This will reject connections above 15 from one source IP.
	
		```
		iptables -A INPUT -p tcp --syn --dport 80 -m connlimit --connlimit-above 15 --connlimit-mask 32 -j REJECT --reject-with tcp-reset  
		```
	* In this 160 new connections (packets really) are allowed before the limit of 150 NEW connections (packets) per second is applied.

		```
		iptables -A INPUT -m state --state RELATED,ESTABLISHED -m limit --limit 150/second --limit-burst 160 -j ACCEPT  
		```