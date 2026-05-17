# fwfeed
Firewall ip blocklist

/ The honeypot all file is plain txt for any purpose, mainly used as a blocklist for incoming connection for public hosts or open port forwards.
File: blocklist_honeypot_ip4_all.txt

/ Honeypot report showing bad actor trends and has a overlap section against other popular blocklists to ask the question - Is this list unique or simply the same as other blocklists  ie why bother, or yes we need it.
File: blocklist_honeypot_firewall_stats.txt

/ 404 report showing some attempts on webhost
File: abuse_ba_404_list.txt

/ ASN abuse report to show trends
File: abuse_asn_log_cidr_5plus_ip.txt

The item is self grown from real ngnix and firewall logging of bad actor IP content using dynamic public IPs that are renewed weekly.


PUBLIC REQUEST
To the large scale service hosting providers like Microsoft, Google, Cloudflare, Let's Encrypt (and other AI and research entities).
Please release a defined list of crawlers or hosts that your services essentially depend on into a dedicated ip lists file and keep it updated, there are so many bad actor data crawlers lurking within or using your services today that your services are now part of the bad actor problem (SSL, compute, hosting etc).

** some of these companies do have listed IP ranges, but not specific to roles ie Microsoft has azure but does not list a web crawler or chatgpt ip list so bad actors sit in the same subnets using rented compute space.


