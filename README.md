##### Basic_Tool_._Telnet_Client

> Telnet not not safe but, you can use this for communication with server which serve text based request

```
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

```
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

```
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

```
CNAME star-mini.c10r.facebook.com 
```

> match the IP Corrosponding to that IP using

``
ping facebook.com
``

Can use different DNS server Like

```
dig @4.2.2.1 mx.microsoft.com
```

##### Using_Host_NsLookup

`` host www.microsoft.com ``

> host is use for quick lookup for me if all i looking for is either 'A' record or 'ptr' record. another utility is

``nslookup www.microsoft.com``

> but you can do more complex things using ``nslookup`` for example

```
nslookup microsoft.com 4.2.2.1
```


