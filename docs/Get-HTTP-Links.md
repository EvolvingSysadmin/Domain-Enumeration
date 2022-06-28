# Get HTTP Links

## Table of Contents
- [Background](#background)
- [Use Case](#use-case)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Resources](#resources)

## Background

## Use Case

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