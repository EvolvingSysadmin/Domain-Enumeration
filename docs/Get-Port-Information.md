# Get Port Information

## Topics

- [Background](#background)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Resources](#resources)

## Background

## Use Case

## Prerequisites

- Install the latest version of Python 3
- Use PIP to install Scapy: `pip install --pre scapy[basic]`
- Install any platform specific dependencies https://scapy.readthedocs.io/en/latest/installation.html#platform-specific-instructions
- Run scapy with root permissions, for instance in an administrative cokmmand prompt

## Usage

Start Scapy:
```C:\>scapy```

Run SYN Scans
```
sr1(IP(dst="72.14.207.99")/TCP(dport=80,flags="S"))
```

The above will send a single SYN packet to Google’s port 80 and will quit after receiving a single response:

Use either notations to scan ports 400 through 443 on the system:
```
sr(IP(dst="192.168.1.1")/TCP(sport=666,dport=(440,443),flags="S"))
```

```
sr(IP(dst="192.168.1.1")/TCP(sport=RandShort(),dport=[440,441,442,443],flags="S"))
```

https://resources.infosecinstitute.com/topic/port-scanning-using-scapy/

https://gist.github.com/mic159/c7133509af81dad409b79b8c4838f4bd 

## Resources
-[Scapy Documentation](https://scapy.readthedocs.io/en/latest/)
-[Scapy GitHub Repository](https://github.com/secdev/scapy)
- [Scapy Project Page](https://github.com/secdev/scapy)