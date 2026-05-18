# fwfeed
Firewall ip blocklist 

Our honeypot loggers are based in New Zealand, the blocklist is self grown from real nginx and firewall logging of bad actor IP content using dynamic public IPs that are renewed weekly.

I was always interested to know if the popular blocklists were actually effective or just statistics for sales purposes, thats even before we know if they are up to date so this was created to measure blocklist effectiveness.

blocklist_honeypot_ip4_all.txt - The honeypot is plain txt for any purpose, mainly used as a blocklist for incoming connection for public hosts or open port forwards.

blocklist_honeypot_firewall_stats.txt - Honeypot report showing bad actor trends and has a overlap section against other popular blocklists to ask the question - Is this list unique or simply the same as other blocklists  ie why bother, or yes we need it.

abuse_ba_404_list.txt - 404 report showing some attempts on webhost.

abuse_asn_log_cidr_5plus_ip.txt - ASN abuse report to show trends.


WHITELIST A IP ADDRESS
See link https://doesnotcompute.supportu.nz/ip-address-lookup-honeypot

PREDICTIVE BLOCKLISTS
I do have service for predictive blocklists based on patterns detected to prevent zero day compromises.
reach out to datatwolimited@gmail.com, MSPs and security focused individuals see report https://github.com/sky-poppy/fwfeed/blob/main/blocklist_honeypot_firewall_stats.txt


PUBLIC REQUEST
To the large scale service hosting providers like Microsoft, Google, Cloudflare, Let's Encrypt (and other AI and research entities).
Please release a defined list of crawlers or hosts that your services essentially depend on into a dedicated ip lists file and keep it updated, there are so many bad actor data crawlers lurking within or using your services today that your services are now part of the bad actor problem (SSL, compute, hosting etc).

** some of these companies do have listed IP ranges, but not specific to roles ie Microsoft has azure but does not list a web crawler or chatgpt ip list so bad actors sit in the same subnets using rented compute space.
