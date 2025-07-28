## Subdomain Takeover

This usually happens when a company has a subdomain, such as blog.example.com, and it points to a 3rd party service that hosts blogs.  If the company stops using that service, they get rid of the subdomain and stop using the service but sometimes they will forget to remove the DNS record for that.

If we're able to get that subdomain and put up a website, anyone visiting that subdomain will be given our page with whatever we have served up on it.

This is a good topic to continue to research on but the course did not go much more into it than this.


## Vulnerable Components

It's very common today for developers to include things such as libraries and other code that has already been written.  This makes development time significantly less but also leads to possible vulnerabilities as the library or code source that is being used may have vulnerabilities baked in or outdated.

List the 3rd party apps being used (by using wappalyzer or other programs) and use that info to search for CVE or other known vulnerabilities in those apps.
