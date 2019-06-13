##### Basic_Tool_._Telnet_Client

> Telnet not not safe but, you can use this for communication with server which serve text based request

```sh
root@kali:~# telnet www.microsoft.com 80  <------ type this 1st
Trying 184.30.58.30...
Connected to e13678.dspb.akamaiedge.net.
Escape character is '^]'.
GET / HTTP/1.1 <------- type this 2nd
Host: www.microsoft.com <------- type this 3rd

// below the response from microsoft server

HTTP/1.1 200 OK
Server: Apache
ETag: "6082151bd56ea922e1357f5896a90d0a:1425454794"
Last-Modified: Wed, 04 Mar 2015 07:39:54 GMT
Accept-Ranges: bytes
Content-Length: 1020
Content-Type: text/html
Date: Sat, 02 Feb 2019 14:58:51 GMT
Connection: keep-alive

<html><head><title>Microsoft Corporation</title><meta http-equiv="X-UA-Compatible" content="IE=EmulateIE7"></meta><meta http-equiv="Content-Type" content="text/html; charset=utf-8"></meta><meta name="SearchTitle" content="Microsoft.com" scheme=""></meta><meta name="Description" content="Get product information, support, and news from Microsoft." scheme=""></meta><meta name="Title" content="Microsoft.com Home Page" scheme=""></meta><meta name="Keywords" content="Microsoft, product, support, help, training, Office, Windows, software, download, trial, preview, demo,  business, security, update, free, computer, PC, server, search, download, install, news" scheme=""></meta><meta name="SearchDescription" content="Microsoft.com Homepage" scheme=""></meta></head><body><p>Your current User-Agent string appears to be from an automated process, if this is incorrect, please click this link:<a href="http://www.microsoft.com/en/us/default.aspx?redir=true">United States English Microsoft Homepage</a></p></body></html>
^CConnection closed by foreign host.
root@kali:~# ^C


```

##### [Basic_Tool_._NetCat](https://null-byte.wonderhowto.com/how-to/hack-like-pro-use-netcat-swiss-army-knife-hacking-tools-0148657/)

##### Basic_Tool_._Ping

```sh
# ping google.com
# ping -c 4 google.com
# ping 172.30.42.255 <-- broadcast address [meaning sending packets to all host on the same network].
# ping -p ffaa 172.30.42.1 <-- defining pattern as hex decemal value
# ping -p ffaa -s 800 172.30.42.1 <-- [-s 800] // sending 800bytes each packets
# ping -p ffaa -s 8000 172.30.42.1 <-- sending larger packets // usefull when sending larger data || is system alive or not
```

##### Useful_Browser_Extentions

> Note: use **firefox** instead of **chorme** because chorme won't allow you to do bad things! but firefox does.

- Temperdata <-- help us to capture messages which is going back and forth withen the server
- passiveRecon <-- help us to investigate to our target without an actuall intraction the target itself.
- groundSpeed <-- help us for web testing
- HackBar <-- help us in testing sql injections. XSS holes and site security

##### Useful_Web_Sites

> [IP Calculator / IP Subnetting](http://jodies.de/ipcalc)
> [Geektools](http://www.geektools.com/) <-- allow us to do trace route || also do 'WHOIS'
> [Geo IP Tool](https://geoiptool.com/)
> [EXPLOIT DATABASE](https://www.exploit-db.com/)
> [WAY BACK MACHINE](https://archive.org/web/)

##### Information_Storage_Tool_For_Kali

> casefile <-- for visualization information for better analysis

##### Google_Hacking

> Google hacking is use for **nero** the search result! Google_Hacking Doesn't mean you will break google server and do what ever you want to do!. It usage the specific keyword to nero the result of searches

``Example``

```sh
site:microsoft.com filetype:xls windows 10
inurl: ""
intext: ""
intitle: ""
```

##### Dig

> Dig Cammand use for lookup information of any host. by using this cammand you will get a "CNAME" (
  A canonical name is the properly denoted host name of a computer or network server. A CNAME specifies an alias or nickname for a canonical host name record in a domain name system (DNS) database. In programming, the term "canonical" means "according to the rules."
)

``Example``

> dig www.facebook.com

``output``

```sh
CNAME star-mini.c10r.facebook.com 
```

> match the IP Corrosponding to that IP using

```sh
ping facebook.com
```

Can use different DNS server Like

```sh
dig @4.2.2.1 mx.microsoft.com
```

##### Using_Host_NsLookup

`` host www.microsoft.com ``

> host is use for quick lookup for me if all i looking for is either 'A' record or 'ptr' record. another utility is

```sh 
nslookup www.microsoft.com
```

> but you can do more complex things using ``nslookup`` for example

```sh
nslookup microsoft.com 4.2.2.1
```

##### Using_Web-Based_Tools

> [MX ToolBox](https://mxtoolbox.com/)
> [Web DNS Tools](http://www.webdnstools.com/dnstools/dns-lookup)
> [G Suite Toolbox](https://toolbox.googleapps.com/apps/main/)

##### Passive_Recon

> Passive Recon is a plugin on firefox as an add-on for complete DNS Lookup (just right click on any href) and see the entire result **check this**


##### Passive_Fingerprinting

> p0f

> open some website and let the 'p04' cammand run bhind the browser

> came back and see the terminal

**Note** - the cammand captured the packets when we surff the web


##### Packet_Captures

> how to actually capture packets

```sh
tcpdump 
```
> captures all the packet which coming and going through the network card of the current machine this happens because the network card is in promiscuous mode. which not only track outgoing packets but incoming too.

> you can specifically capture your desire interface by running this cammand

```sh
tcpdump -i eth0 host 172.30.42.1
```

> 172.30.42.1 is your gayway address aka router

```sh
tcpdump -i eth0 port 443
```

> in this example we can see the https traffic because this is come across port 443.

```sh
tcpdump -v -i eth0 port 443
```

> by using flag -v you can see more information about each traffic

**NOTE** > by using this cammand you can see the headers information only

##### Using_Wireshark

> you can capture the packets which is passing through NIC but can't do analysis on that data... . so you can use different software for that

> first capture the data 

```sh
tcpdump -s 0 -w  output.pcap
```

> `-s 0` meaning capture everything

you can use Ctrl + C to kill the terminal after few second of running the above command

> Now open wireshark software with that capture packet `out.pcap` open it.


##### Banner_Grabbing

> able to intract with sevices. because you wanna pull out the banners which application provides. banners will give you the information about a specific appication. that is running on a specific port . and this may give you version information

```sh
telnet 192.168.86.34 21
```

```sh
ctrl + ] -> exit 
```

> netcat is good for listening and UDP Protocal, this below cammand will do exactily the same this what telnet did. but more powerfull than `telnet`

```sh
nc -l 192.168.86.34 21
```

##### Basic_Protocol_Interaction_-_HTTP

```sh
  nc 192.168.86.34 80
  HEAD / HTTP/1.1
  Host: 192.168.86.34
```

``or``

```sh
  nc 192.168.86.34 80
  GET / HTTP/1.1
  Host: 192.168.86.34
```
> Return the html code in terminal

##### Basic_Protocol_Interaction

```sh
  nc 192.168.86.44 21
  user baduser
  pass P4ssw0rd!
  stat
  pwd
  mkd baddirectory
  cwd baddirectory
  pwd
  syst
```

