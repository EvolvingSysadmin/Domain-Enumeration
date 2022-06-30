# Get Subdomain Information

This page describes how to enumerate subdomains of a given domain by using the [subdomain-scanner.py](/programs/subdomain-scanner/subdomain-scanner.py) Python program.

## Topics

- [Background](#background)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Resources](#resources)

## Background

The Domain Name System heirarchy structure allows a domain name to be broken down into parts known as subdomains. Subdomains are defined by editing the DNS zone file for the domain name. Enumerating subdomains for a given domain can denote the domain structure. [subdomain-scanner.py](/programs/subdomain-scanner/subdomain-scanner.py) uses a list of potential subdomain names and the Python requests library to enumerate the subdomains of a given domain name.

## Use Case

Use the subdomain scanner to determine the subdomains for a given domain. Enumerating subdomains can be particularly useful for testing the security of a domain. Internet facing services are often hosted on subdomains, for instance `vpn.domain-name.com`. Enumerating subdomains can be an initial step for testing the security of those services. Only run the domain enumeration tool against domains that have given express permission to do so. Running the domain enumeration tool against websites without permission will likely break the terms of service of that domain.

## Prerequisites

The Python requests package must be installed to utilize the subdomain enumeration functionality. The [latest version of Python 3](https://www.python.org/downloads/) is required to run the Python requests package. The PIP3 Python package manager is required to install the Python requests package. PIP3 is included with the latest version of Python 3.

Use PIP3 to Install the Python requests package by running the following in a terminal:

```
pip3 install requests
```

A list of subdomain names to test must be created in a .txt file, such as [subdomain-list.txt](/programs/subdomain-scanner/subdomain-list.txt). The program will return names from the list that are valid subdomain names of the given domain.

## Usage

The [subdomain-scanner.py](/programs/subdomain-scanner/subdomain-scanner.py) program runs with positional arguments. The last argument is the domain being scanned. The `-l` argument specifies the word list text file. The `-t` argument specifies the number of threads that the program should dedicate to scanning the domain:

```
python subdomain-scanner.py -l subdomain-list.txt -t 10 hackthissite.org
```

The `-h` argument can also be used to display the help message:

```
python subdomain-scanner.py -h
```

The program will ouput the subdomain that it discovers, such as:

```
[+] Discovered subdomain: http://mail.hackthissite.org
```

## Resources
- [Official Python Download](https://www.python.org/downloads/)
- [Python Requests Package](https://pypi.org/project/requests/)
- [subdomain-scanner.py](/programs/subdomain-scanner/subdomain-scanner.py)
- [subdomain-list.txt](/programs/subdomain-scanner/subdomain-list.txtsubdomain-list.txt)
- [subdomain-list-medium.txt](/programs/subdomain-scanner/subdomain-list-medium.txt)
- [subdomain-list-large.txt](/programs/subdomain-scanner/subdomain-list-large.txt)