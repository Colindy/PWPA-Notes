### Subdomain Enumeration

Subdomain is the "www." portion of the address

You can use crt.sh (a website)

%.site.com - the % will act as a wildcard in the search


Some other tools

subfinder - is a cli tool `subfinder -d website.com`  
assetfinder - another cli tool `assetfinder website.com | grep website.com | sort -u > website.txt`  
amass - another cli tool with other capabilities `amass enum -d website.com > website.txt` - This takes a long time to run.  
httprobe - a cli tool to check if a website is active `httprobe -prefer-https`.  You can run this in line via piping to a full command.  (`cat website.txt | grep website.com | sort -u | httprobe -prefer https | grep https > websitealive.txt`)  
gowitness - another cli tool.  You should be running commands in a specific directory in order to save any output and keep it organized.  You'll need to remove the "https://" portion of the list if you've been following.  `gowitness file -f websitealive.txt -P directory --no-http`.  -P for "path" and the directory you made to put these in.  These are screenshots of the webpages.  Sometimes you won't get anything if the page loads slow but you should get a good bit.  

This can all be scripted out in order to run at the beginning of an engagement.		