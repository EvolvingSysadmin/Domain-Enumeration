# Get HTTP Links

This page describes how to use the `http-scanner.py` Python program to enumerate website links.

## Table of Contents
- [Background](#background)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Resources](#resources)

## Background

The `http-scanner.py` Python program crawls website pages to return the internal and external links on that website. `http-scanner.py` automates website link extraction. `http-scanner.py` can be incorporated into other Python programs. Similarly, Python features such as defined variables, defined functions, and loops can be used to obtain website link information.

## Use Case

The `http-scanner.py` program should be used when the links of a website need to be enumerated. Enumerating website links can enable users to identify unknown webpages or malicious links.

Only run `http-scanner.py` against websites that have given express permission to do so. Running the http link scanning tool against websites without permission will likely break the terms of service for that website.

## Prerequisites

The Python HTTP scanner requires the [latest version of Python 3](https://www.python.org/downloads/). The Python HTTP scanner also needs the PIP3 Python package manager, which is included with the latest version of Python 3.

Use PIP3 to install the Python packages required to use the HTTP scanner by running the following in a terminal:

```
pip3 install -r requirements.txt
```

## Usage

The [http-scanner.py](/programs/http-scanner/http-scanner.py) program runs with positional arguments. The last argument is the target domain being scanned. The -m argument specifies the maximum number of links to scan. The default number of links crawled is 30 if no -m argument is specified. For example, all internal and external links will be enumerated for the first 10 internal pages crawled if the -m argument is set to 10:

```
python http-scanner.py -m 10 https://hackthissite.org
```

The HTTP scanner outputs a .txt file with internal links of the target domain pages and another .txt file with external links from the target domain pages. For instance, for the scan `python http-scanner.py -m 10 https://hackthissite.org` will enumerate internal links in the file www.hackthissite.org_internal_links.txtand will enumerate external links to the file www.hackthissite.org_external_links.txt.

## Resources
- [Official Python Download](https://www.python.org/downloads/)
- [http-scanner.py](/programs/http-scanner/http-scanner.py)
- [http-scanner.py requirements file](/programs/http-scanner/requirements.txt)