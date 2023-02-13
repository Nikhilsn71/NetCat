## NetCat
Netcat is a Unix utility which reads and writes data across network connections using TCP or UDP protocol. 

### Tasks that can be done with NetCat:

* Connect to a port of a target host.
* Listen to a certain port for any inbound connections.
* Send data across client and server once the connection is established.
* Transfer files across the network once the connection is established.
* Can execute programs and scripts of the client on the server and vice versa.
* Can Provide remote shell access of server to a client where shell commands can be executed.


## For Windows

[`<Download />`](https://sourceforge.net/projects/nc110/)

## Installation for linux

```js
apt install netcat-traditional
```
or

```js
sudo apt-get install netcat-traditional
```

## A simple client-server connection:

Type this command on the machine terminal. 
1. To perform simple chat.

```sh
## command for terminal 1
nc -l -p 8080
```

```sh
## command for terminal 2
nc 127.0.0.1 8080
```

2. To perform file transfer.

```sh
## command for terminal 1
nc -v -w 30 -l -p 8080 >file.txt
```

```sh
## command for terminal 2
nc -v -w 2 127.0.0.1 8080<file.txt
```

## Netcat Command Flags
```js
nc -4 – use IPv4 only

nc -6 – use IPv6

nc -u – use UDP instead of TCP

nc -k -l – continue listening after disconnection

nc -n – skip DNS lookups

nc -v – provide verbose output
```


## Netcat Port Scanner
```js
nc -zv site.com 80 – scan a single port

nc -zv hostname.com 80 84 – scan a set of individual ports

nc -zv site.com 80-84 – scan a range of ports
```

## Netcat Banners
```js
echo “” | nc -zv -wl [host] [port range] – obtain the TCP banners for a range of ports
```

## Netcat Backdoor Shells
```js
nc -l -p [port] -e /bin/bash – run a shell on Linux

nc -l -p [port] -e cmd.exe – run a shell for Windows
```

### NetCat Help Commands:

```js
$ netcat -h
```

```js
connect to somewhere:   nc [-options] hostname port[s] [ports] ... 
listen for inbound:     nc -l -p port [-options] [hostname] [port]
options:
 -c shell commands       as `-e'; use /bin/sh to exec [dangerous!!]
        -e filename             program to exec after connect [dangerous!!]
        -b                      allow broadcasts
        -g gateway              source-routing hop point[s], up to 8
        -G num                  source-routing pointer: 4, 8, 12, ...
        -h                      this cruft
        -i secs                 delay interval for lines sent, ports scanned
        -k                      set keepalive option on socket
        -l                      listen mode, for inbound connects
        -n                      numeric-only IP addresses, no DNS
        -o file                 hex dump of traffic
        -p port                 local port number
        -r                      randomize local and remote ports
        -q secs                 quit after EOF on stdin and delay of secs
        -s addr                 local source address
        -T tos                  set Type Of Service
        -t                      answer TELNET negotiation
        -u                      UDP mode
        -v                      verbose [use twice to be more verbose]
        -w secs                 timeout for connects and final net reads
        -C                      Send CRLF as line-ending
        -z                      zero-I/O mode [used for scanning]
```


