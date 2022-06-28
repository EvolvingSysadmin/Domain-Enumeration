# Get Domain Name Information

This page describes how to obtain domain information by using the WHOIS Python library.

## Topics

- [Background](#background)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
  - [Validate Domain Name](#validate-domain-name)
  - [Get Domain Registrar](#get-domain-registrar)
  - [Get Domain Creation Date](#get-domain-creation-date)
  - [Get Domain Expiration Date](#get-domain-expiration-date)
  - [Get Domain Registration Email](#get-domain-registration-email)
  - [Get Domain Registration Location](#get-domain-registration-location)
  - [Get All Domain Registration Information](#get-all-domain-registration-information)
- [Resources](#resources)

## Background

WHOIS is an Internet protocol for retrieving a record of domain name registration information. The [Python WHOIS package](https://pypi.org/project/python-whois/) uses Python to query and parse domain registration information. The registration information that can be obtained using the WHOIS Python library includes whether the domain is registered, the domain registrar, domain creation date, domain expiration date, and address of the domain owner.

## Use Case

The Python WHOIS package should be used when there is a need to obtain information about a domain name. The Python WHOIS package functions can be run individually to obtain specific domain name information or can be included within a larger Python program.

## Prerequisites

The Python WHOIS package must be installed to utilize the domain name lookup functions. The [latest version of Python 3](https://www.python.org/downloads/) is required to run the Python WHOIS package. The PIP3 Python package manager is required to install the Python WHOIS package. PIP3 is included with the latest version of Python 3.

Use PIP3 to Install the Python WHOIS package by running the following in a terminal:
```
pip3 install python-whois
```

Use an import statement to install the Python WHOIS package at the beginning of the Python code:
```
import whois
```

## Usage

Use the code below to complete each task using the WHOIS Python package. The information may not be filed with the domain registrar if a validated domain does not return the requested information.

### Validate Domain Name

Create the `check_registration` function using the Python WHOIS package to determine if a domain name is registered:
```
def check_registration(domain_name):
    try:
        w = whois.whois(domain_name)
    except Exception:
        return False
    else:
        return bool(w.domain_name)
```

Use the `check_registration` function to validate registration of a list of domains by using an if else statement:
```
domains = [
    "amazon.com",
    "github.com",
    "notadomain.com",
    "thisisntregistered.net"
]

for domain in domains:
    print(domain, "is registered" if check_registration(domain) else "is not registered")
```

### Get Domain Registrar

Use the `check_registration` function to return the domain name registrar:

```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
    print("Domain registrar:", whois_info.registrar)
```

### Get Domain Creation Date

Use the `check_registration` function to return the domain name creation date:
```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
    print("Domain creation date:", whois_info.creation_date)
```

### Get Domain Expiration Date

Use the `check_registration` function to return the domain name expiration date:

```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
    print("Expiration date:", whois_info.expiration_date)
```

### Get Domain Registration Email

Use the `check_registration` function to return the domain name registration email address:

```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
print("email addresses:", whois_info.emails)
```

### Get Domain Registration Location

Use the `check_registration` function to return the domain name registration location:

```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
    print("address:", whois_info.address)
    print("city:", whois_info.city)
    print("state:", whois_info.state)
    print("zip code:", whois_info.zipcode)
    print("country:", whois_info.country)
```

### Get All Domain Registration Information

Use the `check_registration` function to return all domain name registration information:

```
domain_name = "github.com"
if check_registration(domain_name):
    whois_info = whois.whois(domain_name)
    print(whois_info)
```

## Resources
- [Official Python Download](https://www.python.org/downloads/)
- [Python WHOIS Package](https://pypi.org/project/python-whois/)