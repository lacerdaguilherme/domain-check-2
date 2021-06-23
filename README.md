Domain Expiration Check Shell Script
====================================
A simple shell script to display or notify the user via email about domain status and expiry date. 

Installation:
-------------
Use the curl or wget command to grab script as follows:

```
$ wget https://raw.githubusercontent.com/lacerdaguilherme/domain-check-2/master/domain-check-2.sh
## [ sample domain list for testing purpose ] ##
$ wget https://raw.githubusercontent.com/lacerdaguilherme/domain-check-2/master/domain-list.txt 
## [ install it in /usr/local/bin dir ] ##
$ sudo cp -vf domain-check-2.sh /usr/local/bin/domain-check-2
$ sudo chmod +x /usr/local/bin/domain-check-2.sh
```

Usage:
------
Run it as follows:
```
$ domain-check-2 -d google.com.br
$ domain-check-2 -d pop.com.br
$ domain-check-2 -f domain-list.txt 
```
Sample outputs:
```
Domain                              Registrar                                      Status   Expires     Days Left
----------------------------------- ---------------------------------------------- -------- ----------- ---------
google.com.br                       Google Brasil Internet Ltda                    Valid    18-may-2023   694  
pop.com.br                          POP Internet LTDA                              Valid    09-aug-2021   47   
correiodopovo.com.br                Empresa Jornalistica Caldas Junior             Valid    05-mar-2022   255  
vivo.com.br                         TELEFÔNICA BRASIL S.A                          Valid    11-may-2023   687  
vivotools.com.br                    POP Internet LTDA                              Valid    07-jan-2024   928  
pruma.com.br                        Bernardo Sá Barreto Pimentel Trancoso          Valid    28-aug-2021   66   
terra.com.br                        Terra Networks Brasil S.A.                     Valid    30-nov-2027   2351 
uol.com.br                          Universo Online S.A.                           Valid    24-apr-2023   670  
```
[Setup Unix/Linux cron job](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)  as follows to get email notification to send expiration notices:

```
@daily /path/to/domain-check-2.sh -f /path/to/your-domains.txt -e you@example.com
```
Getting help
------------
```
$ domain-check-2.sh -h
Usage: domain-check-2.sh [ -e email ] [ -x expir_days ] [ -q ] [ -a ] [ -h ]
          {[ -d domain_namee ]} || { -f domainfile}

  -a               : Send a warning message through email 
  -d domain        : Domain to analyze (interactive mode)
  -e email address : Email address to send expiration notices
  -f domain file   : File with a list of domains
  -h               : Print this screen
  -s whois server  : Whois sever to query for information
  -q               : Don't print anything on the console
  -x days          : Domain expiration interval (eg. if domain_date < days)
```

Authors:
--------
* Origianl Author: Matty < matty91 at gmail dot com > https://github.com/Matty9191
* Forked and maintained by nixCraft https://www.cyberciti.biz/tips/domain-check-script.html https://github.com/nixcraft/domain-check-2
* Added support for .br domains by lacerdaguilherme - 06-2021
