# Footprinting and Network Enumeration

A practical penetration-testing reconnaissance project completed as part
of the **Week 2 assignment of the Networkwalks internship**. This
project demonstrates domain footprinting and network enumeration using
Kali Linux tools.

> **Important:** All activities described in this project were performed
> only against systems for which written permission had been obtained or
> systems owned by the author. Do not scan, enumerate, or access systems
> without explicit authorization.

## Project Overview

Footprinting is an information-gathering phase of penetration testing.
It collects publicly available information about a target domain and
helps build an initial understanding of its internet-facing presence.

This project documents reconnaissance against `networkwalks.com` and
network discovery on the author's own local LAN. The activities include
domain registration lookup, web technology fingerprinting, DNS
enumeration, HTTP header inspection, WAF detection, search-engine
reconnaissance, and local network scanning.

## Objectives

-   Gather publicly available domain registration information.
-   Identify web technologies associated with the target domain.
-   Resolve domain names and inspect DNS information.
-   Review HTTP response headers.
-   Check for the presence of a Web Application Firewall (WAF).
-   Discover publicly indexed information using search techniques.
-   Identify email addresses and subdomains associated with an
    organization.
-   Discover live hosts on an authorized local network.

## Scope and Authorization

**Targets documented in the report:** 1. `networkwalks.com` --- assessed
with written permission. 2. The author's own local LAN --- owned
environment.

The scope must be confirmed before testing. Do not use these procedures
against third-party systems without explicit written authorization.

## Tools and Technologies

  -----------------------------------------------------------------------
  Tool                                Purpose
  ----------------------------------- -----------------------------------
  Kali Linux / Windows                Operating systems used during
                                      reconnaissance

  WHOIS                               Retrieve domain registration
                                      details, dates, and name servers

  WhatWeb                             Fingerprint web technologies,
                                      server details, CMS, and plugins

  nslookup                            Resolve domain names through DNS

  curl                                Inspect HTTP response headers

  wafw00f                             Detect whether a Web Application
                                      Firewall may be protecting a
                                      website

  dnsrecon                            Enumerate DNS records such as NS,
                                      MX, SPF, TXT, and SRV

  Zenmap (Nmap GUI)                   Discover live hosts and inspect IP
                                      and MAC addresses on the local
                                      subnet

  GHDB                                Use Google search operators to
                                      locate publicly indexed information

  TheHarvester                        Gather publicly available email
                                      addresses and subdomains
  -----------------------------------------------------------------------

## Methodology

### 1. WHOIS Lookup

WHOIS is used to collect domain registration information, such as
registrar details, registration dates, and name servers.

``` bash
whois networkwalks.com
```

### 2. Web Technology Fingerprinting with WhatWeb

WhatWeb identifies technologies used by a website, which may include its
web server, CMS, and plugins.

``` bash
whatweb networkwalks.com
```

### 3. DNS Lookup with nslookup

`nslookup` resolves a domain name and displays DNS-related information.

``` bash
nslookup networkwalks.com
```

### 4. HTTP Header Inspection with curl

The report uses curl to inspect the HTTP response returned by the target
website.

``` bash
curl -i https://networkwalks.com
```

Review the response headers for information provided by the server.
Treat exposed technology details as reconnaissance observations, not
automatically as vulnerabilities.

### 5. WAF Detection with wafw00f

Wafw00f is used to check whether a Web Application Firewall is detected
in front of the website.

``` bash
wafw00f https://networkwalks.com
```

### 6. DNS Enumeration with dnsrecon

DNSRecon is used to enumerate DNS records associated with the domain.

``` bash
dnsrecon -d networkwalks.com
```

The report identifies record categories including NS, MX, SPF, TXT, and
SRV.

### 7. TheHarvester --- Baidu Source

TheHarvester is used to gather publicly available information, including
email addresses and subdomains. The report documents a search using the
Baidu source.

### 8. TheHarvester --- All Sources

The report also documents a TheHarvester reconnaissance run using the
`all` source selection.

> The original report does not specify the complete TheHarvester command
> or its configuration. Use the installed version's help output to
> confirm supported options before running it.

### 9. Local Network Enumeration with Zenmap

Zenmap, the graphical interface for Nmap, is used to scan the author's
authorized local subnet and identify live hosts, IP addresses, and MAC
addresses.

Perform this activity only on a network you own or have explicit
permission to assess. Select the correct local subnet and an appropriate
scan profile in Zenmap.

### 10. Google Hacking Database (GHDB)

The report demonstrates a Google search operator intended to locate
publicly indexed webcam-related pages:

``` text
intitle:"Webcam" inurl:WebCam.htm
```

The report also references:

https://www.skylinewebcams.com/en/webcam.html

This is a search-technique demonstration, not authorization to access,
control, or interfere with any webcam. Only review information that is
publicly accessible and within the authorized scope.

## Project Workflow

1.  Confirm written authorization and define the assessment scope.
2.  Collect domain registration information using WHOIS.
3.  Fingerprint web technologies using WhatWeb.
4.  Resolve the domain using nslookup.
5.  Inspect HTTP response headers using curl.
6.  Check for WAF detection using wafw00f.
7.  Enumerate DNS records using DNSRecon.
8.  Gather publicly available email and subdomain information using
    TheHarvester.
9.  Perform authorized local network discovery using Zenmap.
10. Demonstrate search-based reconnaissance using GHDB.
11. Document observations and maintain evidence of the assessment.

## Results and Evidence

The accompanying project report contains screenshots and command outputs
for the reconnaissance activities.

This README describes the methodology. It does not claim specific
discovered IP addresses, email addresses, subdomains, vulnerabilities,
or WAF results that are not reproduced here.

## Key Learning Outcomes

-   Understanding the footprinting phase of penetration testing.
-   Working with domain registration and DNS information.
-   Identifying web technologies through passive and active
    reconnaissance.
-   Inspecting HTTP response headers.
-   Understanding basic WAF detection.
-   Gathering publicly available information using TheHarvester and
    search operators.
-   Discovering devices on an authorized local network using Zenmap.
-   Following authorization and responsible testing practices.

## Legal Disclaimer

This project is intended for educational and research purposes only.

All testing must be conducted on systems and networks that you own or
for which you have explicit written authorization. Unauthorized access,
scanning, enumeration, or exploitation may violate applicable laws and
can result in legal consequences.

The author is not responsible for misuse of the techniques documented in
this repository. You are solely responsible for ensuring that your
activities comply with applicable laws, policies, and permissions.

## Author

**Sudip Patra**

-   LinkedIn: [Sudip Patra](https://www.linkedin.com/in/sudip-patra003/)

------------------------------------------------------------------------

*Project: Footprinting and Network Enumeration --- Week 2, Networkwalks
Internship.*
