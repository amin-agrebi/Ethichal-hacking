3-2 NMap:
The following link has information on setting up the MSF DB in Kali:
https://www.offensive-security.com/metasploit-unleashed/using-databases/

NMap includes a flag to scan the top n services. For example, the top 100 services:
```
nmap -sS -p 80,443,8080,8443,22 142.250.180.142

nmap -sS --top-ports 100
```
Or in XML:
```
nmap -oX - --top-ports 1000 | grep services
```

You can also sort the nmap services file by frequency:
```
sort -r -k3 /usr/share/nmap/nmap-service | head -n 100
```

Personally, I have a set of services lists that I use regularly. Find out what works for you, save it, rinse, and repeat.

3-3 NSE:
https://nmap.org/nsedoc/scripts/
