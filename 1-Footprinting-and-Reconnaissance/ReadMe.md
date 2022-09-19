# <u> Reconnaissance and Footprinting</u>

> ⚡︎ **This chapter have Created by Engineer Ameen Alaquarbi [Whatsapp](https://api.whatsapp.com/send?phone=21621804505)**

## <u>Footprinting</u>
Footprinting is a part of reconnaissance process which is used for gathering possible information about a target computer system or network. 

When used in the computer security lexicon, "Footprinting" generally refers to one of the pre-attack phases; tasks performed before doing the actual attack. **Some of the tools used for Footprinting are Sam Spade, nslookup, traceroute, Nmap and neotrace.**

## Footprinting Types: <u>Active and Passive</u>

- **Active** - requires attacker to touch the device or network
  - Social engineering and other communication that requires interaction with target
- **Passive** - measures to collect information from publicly available sources
  - Websites, DNS records, business information databases

### Footprinting helps to:

- **Know Security Posture** – The data gathered will help us to get an overview of the security posture of the company such as details about the presence of a firewall, security configurations of applications etc.

- **Reduce Attack Area** – Can identify a specific range of systems and concentrate on particular targets only. This will greatly reduce the number of systems we are focussing on.

- **Identify vulnerabilities** – we can build an information database containing the vulnerabilities, threats, loopholes available in the system of the target organization.

- **Draw Network map** – helps to draw a network map of the networks in the target organization covering topology, trusted routers, presence of server and other information.

Footprinting could be both **passive** and **active**. Reviewing a company’s website is an example of passive footprinting, whereas attempting to gain access to sensitive information through social engineering is an example of active information gathering.

During this phase, a hacker can collect the following information (only high-level information):

- **Domain name**
- **IP Addresses**
- **Namespaces**
- **Employee information**
- **Phone numbers**
- **E-mails**
- **Job Information**

Can be:
  - **Anonymous** - information gathering without revealing anything about yourself
  - **Pseudonymous** - making someone else take the blame for your actions

**Competitive Intelligence** - information gathered by businesses about competitors

**Alexa.com** - resource for statistics about websites

## Footprinting Objectives

- **Network**
  - DNS
  - IP networks
  - Acessible Systems
  - Websites 
  - Access Control 
  - VPN Endpoints 
  - Firewall vendors 
  - IDS Systems 
  - Routing/Routed Protocols 
  - Phone System (Analog/VoIP) 

- **Organization**
  - Org Structure
  - Websites
  - Phone Numbers
  - Directory Information
  - Office Locations
  - Company History
  - Business Associations

- **Hosts**
  - Listening Services
  - Operating System Versions
  - Internet Reachability
  - Enumerated Information
  - SNMP Info
  - Users/Groups
  - Mobile Devices

## <u>Methods and Tools</u>

### Search Engines

- **[NetCraft](https://www.netcraft.com/)** - Blueprint a comprehensive list of information about the technologies and information about target website.
  - ![netcraft](https://i0.wp.com/hackingblogs.com/wp-content/uploads/2018/01/Capture-min-2.png)
- **Job Search Sites** - Information about technologies can be gleaned from job postings.
- **Google search | Google dorks:** 
  - `filetype:`  - looks for file types
  - `index of` - directory listings
  - `info:` - contains Google's information about the page
  - `intitle:` - string in title
  - `inurl:` - string in url
  - `link:` - finds linked pages
  - `related:` - finds similar pages
  - `site:` - finds pages specific to that site
    - **Example**:
    - ![google-dorks](https://miro.medium.com/max/659/0*GGRvHnh59qi5lVB9.png)
  - [GHDB](https://www.exploit-db.com/google-hacking-database) is very good for learn Google Dorks and how it's done in real world scenario 
- **Metagoofil** - Command line interface that uses **Google hacks** to find information in meta tags (domain, filetype, etc; Is a google dorks for terminal).

### Website Footprinting

- **Web mirroring | Website Cloning** - allows for discrete testing offline
  - **HTTrack** - *you can use the CLI version or Web Interface version*
  - **Wget** - Linux command 
    - `wget -mk -w 10 http://hackthissite.org/`
  - **Black Widow**
  - **WebRipper**
  - **Teleport Pro**
  - **Backstreet Browser**
- **Archive.org / [Wayback machine](https://archive.org/web/)** 
- Provides cached websites from various dates which possibly have sensitive information that has been now removed.
  - **Wayback Machine -> Google.com**:
    - ![wayback](https://searchengineland.com/figz/wp-content/seloads/2011/01/archive41-500x256.png)

### Email Footprinting

- **Email  header** - may show servers and where the location of those servers are
  - Email headers can provide: **Names, Addresses (IP, email), Mail servers, Time stamps, Authentication and so on.**
    - ![emailheader](https://www.wikihow.com/images/thumb/7/72/Read-Email-Headers-Step-7.jpg/v4-460px-Read-Email-Headers-Step-7.jpg.webp)
  - **EmailTrackerPro** is a Windows software that trace an email back to its true point of origin:
    - ![emailtrackerpro](http://www.emailtrackerpro.com/support/v9/tutorials/images/traceheader/3.png)
- **Email tracking** - services can track various bits of information including the IP address of where it was opened, where it went, etc.

### DNS Footprinting

- Ports

  - Name lookup - UDP 53
  - Zone transfer - TCP 53

- Zone transfer replicates all records

- **Name resolvers** answer requests

- **Authoritative Servers** hold all records for a namespace

- **DNS Record Types**

  - | Name  | Description        | Purpose                                        |
    | ----- | ------------------ | ---------------------------------------------- |
    | SRV   | Service            | Points to a specific service                   |
    | SOA   | Start of Authority | Indicates the authoritative NS for a namespace |
    | PTR   | Pointer            | Maps an IP to a hostname                       |
    | NS    | Nameserver         | Lists the nameservers for a namespace          |
    | MX    | Mail Exchange      | Lists email servers                            |
    | CNAME | Canonical Name     | Maps a name to an A reccord                    |
    | A     | Address            | Maps an hostname to an IP address              |

- **DNS Poisoning** - changes cache on a machine to redirect requests to a malicious server

- **DNSSEC** - helps prevent DNS poisoning by encrypting records

- **SOA Record Fields**

  - **Source Host** - hostname of the primary DNS
  - **Contact Email** - email for the person responsible for the zone file
  - **Serial Number** - revision number that increments with each change
  - **Refresh Time** - time in which an update should occur
  - **Retry Time** - time that a NS should wait on a failure
  - **Expire Time** - time in which a zone transfer is allowed to complete
  - **TTL** - minimum TTL for records within the zone

- **IP Address Management**

  - **ARIN** - North America
  - **APNIC** - Asia Pacific
  - **RIPE** - Europe, Middle East
  - **LACNIC** - Latin America
  - **AfriNIC** - Africa

- **Whois** - obtains registration information for the domain from command line or web interface.
  - on Kali, whois is pre-installed on CLI; e.g: `whois google.com`)
  - on Windows, you can use **SmartWhois** GUI software to perform a whois, or any website like domaintools.com
- **Nslookup** - Performs DNS queries; (nslookup is pre-installed on Kali Linux)

  - `nslookup www.hackthissite.org`
  - ```
    Server:         192.168.63.2
    Address:        192.168.63.2#53

    Non-authoritative answer:
    Name:   www.hackthissite.org
    Address: 137.74.187.103
    Name:   www.hackthissite.org
    Address: 137.74.187.102
    Name:   www.hackthissite.org
    Address: 137.74.187.100
    Name:   www.hackthissite.org
    Address: 137.74.187.101
    Name:   www.hackthissite.org
    Address: 137.74.187.104
    ```
    - First two lines shows my current DNS server; The IP addresses returned are '**A record**', meaning is the IPvA address of the domain; Bottom line NsLookup queries the specified DNS server and retrieves the requested records that are associated with the domain. 

    - **The following types of DNS records are especially useful to use on Nslookup:**


    - | Type  | Description        |
      | ----- | ------------------ |
      | A     |  the IPv4 address of the domain          |
      | AAAA  |  the domain’s IPv6 address          |
      | CNAME |  the canonical name — allowing one domain name to map on to another. This allows more than one website to refer to a single web server.          | 
      | MX    |  the server that handles email for the domain.        |
      | NS    |  one or more authoritative name server records for the domain.          | 
      | TXT   |  a record containing information for use outside the DNS server. The content takes the form name=value. This information is used for many things including authentication schemes such as SPF and DKIM.          |

  - **Nslookup - Interactive mode zone transfer** (Interactive mode allows the user to query name servers for information about various hosts and domains or to print a list of hosts in a domain).
    - `nslookup`
    - `server <IP Address>`
    - `set type = <DNS type>`
    - `<target domain>`
  - ```
    nslookup 
    > set type=AAAA                                                                                                                                            
    > www.hackthissite.org
    Server:         192.168.63.2                                                                                                                               
    Address:        192.168.63.2#53                                                                                                                            
                                                                                                                                                              
    Non-authoritative answer:                                                                                                                                  
    Name:   www.hackthissite.org                                                                                                                               
    Address: 2001:41d0:8:ccd8:137:74:187:103                                                                                                                   
    Name:   www.hackthissite.org                                                                                                                               
    Address: 2001:41d0:8:ccd8:137:74:187:102                                                                                                                   
    Name:   www.hackthissite.org                                                                                                                               
    Address: 2001:41d0:8:ccd8:137:74:187:101                                                                                                                   
    Name:   www.hackthissite.org                                                                                                                               
    Address: 2001:41d0:8:ccd8:137:74:187:100
    Name:   www.hackthissite.org
    Address: 2001:41d0:8:ccd8:137:74:187:104
    ```
- **Dig** - unix-based command like nslookup

  - `dig <target>`
  - ```
    dig www.hackthissite.org

    ; <<>> DiG 9.16.2-Debian <<>> www.hackthissite.org
    ;; global options: +cmd
    ;; Got answer:
    ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 51391
    ;; flags: qr rd ra; QUERY: 1, ANSWER: 5, AUTHORITY: 0, ADDITIONAL: 1

    ;; OPT PSEUDOSECTION:
    ; EDNS: version: 0, flags:; MBZ: 0x0005, udp: 4096
    ;; QUESTION SECTION:
    ;www.hackthissite.org.          IN      A

    ;; ANSWER SECTION:
    www.hackthissite.org.   5       IN      A       137.74.187.104
    www.hackthissite.org.   5       IN      A       137.74.187.101
    www.hackthissite.org.   5       IN      A       137.74.187.100
    www.hackthissite.org.   5       IN      A       137.74.187.102
    www.hackthissite.org.   5       IN      A       137.74.187.103

    ;; Query time: 11 msec
    ;; SERVER: 192.168.63.2#53(192.168.63.2)
    ;; WHEN: Tue Aug 11 15:05:01 EDT 2020
    ;; MSG SIZE  rcvd: 129

    ```
  - To get email records specify `-t MX`
    - `dig <target> -t MX`
  - To get zone transfer specify `axfr`

### Network Footprinting

- IP address range can be obtained from regional registrar (e.g: ARIN for America, RIPE for Europe, etc)

- Use `traceroute` to find intermediary servers
  - traceroute uses ICMP echo in Windows (tracert)
  - traceroute is good for detect Firewalls and the network path

**Usage example**:
  - **`traceroute -I nsa.gov`**
    - Specify target: `traceroute <target>`
    - In this case is used ICMP ECHO for tracerouting: `-I`
```
traceroute -I nsa.gov
traceroute to nsa.gov (104.83.73.99), 30 hops max, 60 byte packets
 1  192.168.63.2 (192.168.63.2)  0.194 ms  0.163 ms  0.150 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 9  * * *
10  * * *
11  a104-83-73-99.deploy.static.akamaitechnologies.com (104.83.73.99)  42.742 ms  42.666 ms  25.176 ms

```
> ⚠️ **Windows command - `tracert`**
> ⚠️ **Linux Command - `traceroute`**





## <u>Web Based Recon</u>

### **[NetCraft](https://www.netcraft.com/)**
Netcraft is a website analyzing server, with the help of this website we find basic and important information on the website like:

- **Background** — This includes basic domain information.
  - Which OS, Web server is runing; Which ISP;
- **Network** — This includes information from IP Address to Domain names to nameservers.
- **SSL/TLS** — This gives the ssl/tls status of the target
- **Hosting History** - This gives the information on the hosting history of the target
- **Sender Policy Framework (SPF)** — This describes who can send mail on the domains behalf
- **DMARC** -This is a mechanism for domain owners to indicate how mail purporting to originate from their domain should be authenticated
- **Web Trackers** — This trackers can be used to monitor individual user behavior across the web
Site Technology — This section includes details on:
  - Cloud & PaaS
  - Server-Side technologies (e.g: PHP)
  - Client-Side technologies (e.g: JavaScript library)
  - CDN Information
  - CMS Information (e.g: Wordpress, Joomla, etc)
  - Mobile Technologies
  - Web stats (e.g: Web analytics, collection, etc)
  - Character encoding


![netcraft](https://i0.wp.com/hackingblogs.com/wp-content/uploads/2018/01/Capture-min-2.png)

### **[Shodan](https://www.shodan.io/)**
*Shodan Unlike traditional search engines such as Google, use Web crawlers to traverse your entire site, but directly into the channel behind the Internet, various types of port equipment audits, and never stops looking for the Internet and all associated **servers, camera, printers, routers, and so on**.*

- Some have also described it as a search engine of service banners, which are metadata that the server sends back to the client.

- Shodan works well with basic, single-term searches. Here are the basic search filters you can use:
  - **city:** find devices in a particular city
  - **country:** find devices in a particular country
  - **geo:** you can pass it coordinates
  - **hostname:** find values that match the hostname
  - **net:** search based on an IP or /x CIDR
  - **os:** search based on an operating system
  - **port:** find particular ports that are open
  - **before/after:** find results within a timeframe


![shodan](https://logz.io/wp-content/uploads/2019/05/Shodan.png)
![shodan2](https://securityonline.info/wp-content/uploads/2017/10/shodan-1-615x1024.png)

### **[Censys](https://censys.io/overview/)**
*Alternative for Shodan.*

![censys](https://gist.githubusercontent.com/Samsar4/62886aac358c3d484a0ec17e8eb11266/raw/403be7a4514b6e0af36e0f568328372a5ce09cbf/censys.png)

