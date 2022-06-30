# Get Port Information

This page describes how to obtain port information of a target IP address by using SYN scan with the Scapy Python program.

## Topics

- [Background](#background)
  - [What is Scapy?](#what-is-scapy)
  - [What is SYN Scanning](#what-is-syn-scanning)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Resources](#resources)

## Background

### What is Scapy?

Scapy is a Python program that allows users to create, send, sniff, and dissect network packets. The Python programming language can be used to interact directly with Scapy. For example, Scapy can be used in conjunction with user defined variabless, functions, and loops. Scapy can create and analyze packets of many protocols, including UDP and TCP.

### What is SYN scanning?

SYN scanning is a method for utilizing the TCP three-way handshake to determine the status of a communications port. SYN scanning uses half open scanning to obtain port information without sending a TCP ACK packet to establish a full TCP connection.

## Use Case

Use Scapy to determine the port communications information of a given domain or IP address. Obtaining communications port information can help determine which services are being run from a domain or IP address. Enumerating a domain's services helps to assess the security of those services.

Only run Scapy against IP addresses that have given express permission to do so. Running Scapy against websites without permission will likely break the terms of service for that domain.

## Prerequisites

The following prerequisites are needed to use Scapy:
- Install the latest version of Python 3. The latest version of Python 3 can be downloaded from the [official Python download website](https://www.python.org/downloads/) for the given operating system
- Install the PIP3 Python package manager. The PIP3 package manager is installed by default during the Python 3 installation
- Use PIP to install Scapy by running `pip install --pre scapy[basic]`
- Install any platform specific dependencies listed in the [Scapy documentation](https://scapy.readthedocs.io/en/latest/installation.html#platform-specific-instructions)
- Run scapy with root permissions, for instance in an administrative command prompt in Windows or by using `SUDO` in Linux

## Usage

Use the following instructions to start Scapy and run a SYN scan on a target IP address.

Open a command prompt with administrative permissions and run the following command to start Scapy in Windows:

```
C:\>scapy
Welcome to Scapy (2.4.0)
>>>
```

Initialize a Scapy SYN scan by running the following command. The command creates the SYN scan that stores results as `sr1`. The destination IP address of 137.74.187.102 is specified by using the argument `dst="137.74.187.102"`. The destination scan port of 80 is specified by using the argument `dport=80`. The TCP SYN scan is specified by using the argument `flags="S"`.

```
sr1(IP(dst="137.74.187.102")/TCP(dport=80,flags="S"))
```

Scapy SYN scans can be run against multiple destination ports by including multiple target ports in the `dport` argument. The following command runs a Scapy SYN scan on the destination ports 20, 21, 22, 53, 80, 110, 143, 161, 440, and 443 of IP address 137.74.187.102 and stores the result as `sr2`.

```
sr2(IP(dst="137.74.187.102")/TCP(dport=[20,21,22,53,80,110,143,161,440,443],flags="S"))
```

Scapy includes a `report_ports()` function to automate SYN scans and returns results in LaTeX output which can be used to create reports. Use the following arguments to use the `report_ports()` Scapy function to automate and return SYN scan results on destination ports 80 and 443 for IP address 137.74.187.102:

```
report_ports("137.74.187.102",(80,443))
```

## Resources
- [Official Python Download](https://www.python.org/downloads/)
- [Scapy Documentation](https://scapy.readthedocs.io/en/latest/)
- [Scapy GitHub Repository](https://github.com/secdev/scapy)
- [Scapy Project Page](https://github.com/secdev/scapy)