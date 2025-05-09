### Fingerprinting Website Technologies

builtwith.com - will give you information about the website and what it's built on

Can also be done with the wappalyzer browser app in Firefox.

Are any of the tools out of date?  Anything that can be used to dig deeper in?


Within Kali, we can use the `curl` command

`curl -I https://azena.com`

-L will follow a redirect


Can also use www.securityheaders.com in order to check a websites header information.  This gives you a much cleaner output than the command line output usually does.


Can also use the lovely `nmap` tool.

`nmap -p 80,443 -A azena.com`

