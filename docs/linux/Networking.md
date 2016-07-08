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