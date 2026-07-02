# fwfeed
Firewall ip blocklist 

Our honeypot loggers are based in New Zealand, the blocklist is populated from real webhosts and firewall logging data of bad actor IP content using dynamic public IPs that are renewed weekly.

This feed is not just another recycled IP list; it detects fresh attackers, predicts nearby abuse by CIDR/hosting patterns, and exposes broad scanner infrastructure by showing ASN and port behavior.

Collection sensors use weekly renewed public DHCP addresses. This reduces dependence on a fixed honeypot IP and helps identify broad scanners, opportunistic recon, and bad actors sweeping newly assigned public address space.


I was always interested to know if the popular blocklists were actually effective or just statistics for sales purposes, thats even before we know if they are up to date so this was created to measure blocklist effectiveness.

blocklist_honeypot_firewall_stats.txt - Honeypot report showing bad actor trends and has a overlap section against other popular blocklists to ask the question - Is this list unique or simply the same as other blocklists  ie why bother, or yes we need it.

blocklist_honeypot_ip4_all.txt - The blocklist is plain txt for any purpose, mainly used for incoming connection for public hosts or open port forwards.

blocklist_honeypot_ip4_cidr_agg.txt - CIDR aggregation file, updated less frequently, same content as all.txt file.

abuse_ba_404_list.txt - 404 report showing some invalid file trends on webhosts.

abuse_asn_log_cidr_5plus_ip.txt - ASN abuse report to show trends.

asn_webcrawler_robots_ip.txt - ASN found when IP looking for robots.txt file on webhosts. Added bot or agent name, should be noted most "good intent" crawlers advertise a specific crawl agent name, the rest are web "browser agents" dressed up as mobile or computer web browsers. IP found here are not whitelisted automatically. This is to verify genuine "purposeful" web crawlers vs junk or pretend crawlers showing as "GoogleBot" or "BingBot" in log files.

allow_letsencrypt_ip.txt - Lets Encrypt IPs found in webhost logs.

ASN_BA_EXPORTS folder - Lists of hosts found by port number. See overlap report: https://github.com/sky-poppy/fwfeed/blob/main/asn_ba_port_recent_top50_port_overlap.txt

ASN_CAT_EXPORTS folder - Lists of ASN by entity type with prefix, BGP private, non-routable and reserved ASNs retained in list using prisoner.iana.org IP 192.175.48.1/32.

ASN_GEO_EXPORTS folder - Lists of ASN by country code with prefix.


WHITELIST A IP ADDRESS
See link https://doesnotcompute.supportu.nz/ip-address-lookup-honeypot

WHITELIST SERVICES 
Cloudflare, bingbot, googlebot and a few others like openai, these items have been whitelisted to prevent index searches from being blocked in the event you host a website. Use a robots.txt file to control web crawlers. Use nginx/apache rules to deny unwanted crawlers that ignore robots.txt rules.

PREDICTIVE BLOCKLISTS
I do have service for predictive blocklists based on patterns detected to prevent zero day compromises.
reach out to datatwolimited@gmail.com, MSPs and security focused individuals see report https://github.com/sky-poppy/fwfeed/blob/main/blocklist_honeypot_firewall_stats.txt - See predictive lines within the stats file.

PUBLIC REQUEST
To the large scale service hosting providers like Microsoft, Google, Cloudflare, Let's Encrypt (and other AI and research entities).
Please release a defined list of crawlers or hosts that your services essentially depend on into a dedicated ip lists file and keep it updated, there are so many bad actor data crawlers lurking within or using your services today that your services are now part of the bad actor problem (SSL, compute, hosting etc).

** some of these companies do have listed IP ranges, but not specific to roles ie Microsoft has Azure but does not list a web crawler or chatgpt ip list so bad actors can sit in the same subnets using rented compute space.


SUMMARY FOR PREVENTING ZERO DAY AND MALICIOUS CONNECTIONS
Unless you are hosting a public website or service for global access, then this subject applies to most private access scenarios.

Before authentication any begins or use of stolen credentials are used and MFA requirements come into play is the "new connection" request when thinking about basic network connectivity.


You may have an appliance that has factory set listening ports that you need open for incoming connections, for example SAML or IPSEC and you cannot restrict by 
your Geo region as contractors are roaming from anywhere outside of your local GEOIP region. (GEOIP by country is still a wide allowance considering proxy attacks are now common!)

If you want to block more than 80% of potential and unknown zero day and malicious attacks, block HOSTING, ISP and BUSINESS asn networks as a start for ingress "new connections" for 
listening ports and whitelist your own known trusted services, your ISP and contractor ISP provider subnets as needed. Part of your security information collection should be to know 
where individuals connect from before they attempt to authenticate with your network. 

A VPN only secures traffic for a user once authenticated, using a VPN does not prevent the new connection attempts to use newly discovered attack methods (zero day, not updated firmware etc) to compromise your VPN appliance! 

The reality is if you do not know whom is connecting from where to your services before any authentication occurs, then you are open to attack at anytime.

By restricting "new connections" to your known sources, you resolve a large "unknown" attack surface and turn this into a security policy with a known attack 
surface area you choose to manage. 

Related connections are not the same as ingress "new connections" policies, this is your user or device connecting to a hosted service like M365, Zoom, Dropbox, Google etc
and the hosted service replies to that request so that internet activity behaviour is expected for end users. These services typically reside in the HOSTED and BUSINESS asn's.

With a overview on security, your trusted hosts or ISP whitelisted items are still a possible attack vector but now you have restricted further, if an event occurs 
you know the entry vector how and may restrict access even further before an event occurs or by company policy ie make contractors only use your trusted isp selection for a region as part 
of your t&c's for remote access.
 
Have fun!
