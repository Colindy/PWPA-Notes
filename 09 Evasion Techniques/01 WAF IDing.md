## WAF Identification and Fingerprinting

Web Application Firewall (WAF) is a device that sits on the network between the web application and the internet.  It's generally rule based, meaning that as it watches traffic, it's checking against a set of "rules" that indicate different signatures for specific attacks.

Some WAFs are more sophisticated and judge on baseline and anything abnormal gets flagged.

Some companies deploy it and then don't update it very well so even if there is one, it may not be up to date.

You can try a few different things to try and bypass.

You can FUZZ but some WAFs may block you after so many requests.

You can split the payloads and try to sneak it in that way.

`wafw00f` is a handy tool used to fingerprint a WAF to see what you are dealing with.