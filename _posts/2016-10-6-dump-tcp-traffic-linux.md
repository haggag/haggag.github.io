---
layout: post
title: Dump tcp traffic in Linux
---

A very common task while troublshooting software servers installed on Linux, is to check if they are receiving traffic at all! Many times the problem is the firewall is just blocking the incoming traffic. Not finding this quickly and lead to hours fiddling with configuration files and all sorts of complex things.

The following approach is a very simple way to verify whether some common servers are receiving traffic or not.

The tcpump is a Linux command line tool which helps alot debuging such firewall issues. It can verify if packets are reaching the server.

### E-mail Servers
Verify if ports 587 or 25 are receiving (email) traffic:

```
tcpdump -n -i eth0 'tcp and (port 587 or port 25)'
```


### VPN Servers
Verify if default OpenVPN port is recieving traffic:

```
tcpdump -n -i eth0 'udp and (port 1194)'
```
