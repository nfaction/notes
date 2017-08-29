# Linux Networking
## Tools

<https://sysdig.com/blog/linux-troubleshooting-cheatsheet/>

## TCPDump, WireShark and Tshark

* <https://danielmiessler.com/study/tcpdump/>
* <http://www.thegeekstuff.com/2010/08/tcpdump-command-examples>
* <http://jvns.ca/blog/2016/03/16/tcpdump-is-amazing/>

```
tcpdump -nS -i any -s0
tcpdump -nS -i any -s0 icmp
tcpdump -nS -i any -s0 port 22
tcpdump -nS -i any -s0 port 22 and src 192.168.1.X
tcpdump -i eth1 arp
```

## Routing

<http://www.cyberciti.biz/faq/howto-linux-configuring-default-route-with-ipcommand/>

## DNS Cache

Clearing cache: <https://www.liquidweb.com/kb/flush-dns-cache/>

* Windows

	```
	ipconfig /flushdns
	```

* Mac
	* Mac OS X versions 10.10.4 and newer:
	
		```
		dscacheutil -flushcache; sudo killall -HUP mDNSResponder
		```
		
	* Mac OS X versions 10.10-10.10.3:

		```
		sudo discoveryutil mdnsflushcache; sudo discoveryutil udnsflushcaches
		```
		
	* Mac OS X versions 10.9:

		```
		sudo killall -HUP mDNSResponder
		```

	* Mac OS X versions 10.6-10.8:

		```
		sudo dscacheutil -flushcache
		```
		
* Linux

	```
	sudo nscd -i hosts
	
	OR
	
	sudo nscd -I hosts
	
	# Debian/Ubuntu
	sudo service dns-clean restart
	```
