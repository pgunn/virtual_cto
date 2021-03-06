# DNS and SSL Certs
DNS and SSL certs should be through Gandi (there are plenty of other options too). You'll want at least two domains, one for public purposes, and one for internal use (the latter could be through a public DNS, or could be entirely internal, but they should be distinct). Internal use includes but is not limited to naming systems that are not publicly accessible or meant for public purposes.

I recommend against certbot/letsencrypt; it is a moving part in infrastructure and integrates poorly with a number of services that expect to get a longer-lived cert.

Cert expiry should be managed with a central calendar.

SSL termination should happen at the edge of your network.
