# "What's in a name? Your guide to the wacky world of DNS" by Ashley Sullins

IP addresses are like mobile phone numbers, while DNS names are like the contact name in your contacts list.

## Nameservers

A nameserver receives a domain name and returns the DNS records for that domain name.
Most commonly, nameservers are used to fetch an `A` record, which points to the IP address of the server that hosts the website.


## Before launching DNS changes

* Take a screenshot of the existing settings!
* Do a final smoke test of the production server
* Make sure you have access to change the records


## DNS propagation

There are authoritative DNS servers as well as recursive DNS servers that look up information from the authoritative server.
DNS records are configured with a time to live (TTL) that says how often to check the authoritative DNS server for changes.
Before making changes, setting the TTL to a low value is useful because the DNS will be checked for changes frequently while you're making changes.
Setting it back to a high value afterward is useful so that a DNS query doesn't occur as often as part of your users' requests.
