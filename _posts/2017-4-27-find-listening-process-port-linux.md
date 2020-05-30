---
layout: post
title: Find and terminate listening process on a specific port in Linux
---

A very common error when launching a program that listens on some port is getting "Failed to listen on port X" or "Port X is already in use".

You can know which program is listening on that port by the following command:

```
sudo netstat -peant | grep :443
```
or
```
lsof -i :443
```

The example above assumes you are troubleshooting port 443.

Once you execute any of the previous commands you can get the PID (process id)  of that process and terminate it if needed.
```
sudo kill -9 <PID>
```

To get more info about the process:
```
ps -fp <PID>
```


You can get all active Internet connections (servers and established) by just executing:
```
sudo netstat -peant
```
