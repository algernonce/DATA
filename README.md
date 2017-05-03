# DATA
Credential Phish Analysis and Automation

DATA currently consists of the following scripts:

## Bucklegripper (py)
  - Given a suspected phishing url or file of line separated urls, visit, screenshot, and scrape for interesting files.
  - Requirements can be installed by running or reviewing install_bucklegripper_deps.sh
```
usage: bucklegripper.py [-h] [-u URL] [-s SOURCE] [-r READFILE] [-a USERAGENT]

Visit a suspected phishing page, screenshot it and pillage it for phishing
archives

optional arguments:
  -h, --help            show this help message and exit
  -u URL, --url URL     Url to visit
  -s SOURCE, --source SOURCE
                        Apply a source to where this url came from
  -r READFILE, --readfile READFILE
                        Read in a file of URLs one per line
  -a USERAGENT, --useragent USERAGENT
                        Custom User-Agent
```
Example Usage
```
$ python bucklegripper.py -s openphish -r ../../test_urls.txt

[+] Beginning processing of ../../test_urls.txt

[+] Processing http://onjasela.net/DB/fr/
  [+] Screencapped http://onjasela.net/DB/fr/ as 20170503-010034-openphish-onjasela.net.png

[+] Processing http://suesschool.com/yahoologin/yahoologin/clients/login.php
  [+] Screencapped http://suesschool.com/yahoologin/yahoologin/clients/login.php as 20170503-010053-openphish-suesschool.com.png
[+] Found Opendir at http://suesschool.com/yahoologin/yahoologin/clients/
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/clients/login.php
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/clients/data.php
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/clients/block.php
[+] Found Opendir at http://suesschool.com/yahoologin/yahoologin/
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/login.php
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/data.php
  [+] Found php file: http://suesschool.com/yahoologin/yahoologin/block.php
  [+] Found Zip file at http://suesschool.com/yahoologin.zip
  [+] Saved http://suesschool.com/yahoologin.zip as 20170503-010125-openphish-suesschool.com-yahoologin.zip
[+] Found Opendir at http://suesschool.com/yahoologin/
```

## Bullyblinder (py)
  - While capturing a pcap visit a suspected phishing page. Handle redirectors and obfuscation to find a web form. Scrape the form and make educated guesses at what should be entered into the fields. Submit the form and repeat.
  - Requirements can be installed by running or reviewing install_bullyblinder_deps.sh
```
usage: bullyblinder.py [-h] -u URL [-a USERAGENT] -i INTERFACE

Visit a suspected phishing page and attempt form filling while getting a pcap

optional arguments:
  -h, --help            show this help message and exit
  -u URL, --url URL     Url to visit
  -a USERAGENT, --useragent USERAGENT
                        Custom User-Agent to use
  -i INTERFACE, --interface INTERFACE
                        Interface to tell tshark to listen on
```
## Slickshoes (sh)
  - A basic bash script that pulls links out of pdfs in streams or in clear view.
  
