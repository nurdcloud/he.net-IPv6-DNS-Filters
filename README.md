# he.net-IPv6-DNS-Filters
Various DNS (bind+dnsmasq) rules to disable IPv6 Traffic to certain Sites (eg. Netflix)

Current situation:
Since my provider doesn't provide dual stack IPv4+6 i use a 6in4 tunnel by tunnelbroker.net.
Various websites recognise this as a proxy/vpn service and block me now (Eg. Netflix).
This config files are what i use here in Switzerland and i will update the list as it grows.

Basic Setup:
I run a bind DNS server combined with dnsmask on my private network.
Bind is configured to listen on port 53 as usual and i have set up forwarding zones
as you will find in 'named.conf.local'. 

Dnsmasq is setup to listen on port 5353. Requests to zones as netflix.com will be redirected by
bind to dnsmasq, which will deny IPv6 resolution of these domains.
