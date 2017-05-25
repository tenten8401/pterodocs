---
title: 'Connection Errors'
---

`We were unable to connect to the main Socket.IO server, there may be network issues currently. The panel may not work as expected.`

Or if your node at `List Nodes` does not show a green heart / you cannot send any commands to your servers, have a look at this list of common issues:

1. Check if the daemon is running by using `service wings status`
2. Check if the daemon ports are open in your firewall (port 8080, e.g. netstat -tunlp | grep 8080 (port 2022 for sftp))
3. Check if your panel can reach the daemon with the FQDN (Domain) you configured (`tracepath` / `ping` / `nslookup` / `curl`)
4. Check your DNS settings (nslookup PANEL_DOMAIN.tld and nslookup DAEMON_DOMAIN.tld; make sure that the IP's you get are correct)
5. Check what the output of your browser console F12 (the console shows the issue in most cases / the support staff also needs the output)
6. Check if your setup the daemon and correctly implemented the `core.json` contents
7. Check if you accidentally run the daemon using https while setting http in the panel or vice versa
8. If you use CloudFlare make sure that the "Cloud mode (the yellow cloud)" for your daemons A record (or panels A record) is disabled.
9. Stop the daemon and do `cd /srv/daemon; npm start` and post the output to @support-team if you see any errors in there
10. Make sure your server is connected to the inter- or intranet and is reachable
11. Make sure when using the daemon behind a firewall (like pfSense or OpenSwitch) that you have the correct NAT settings to access your daemons ports from the outside network
12. If nothing works -> Check your own DNS / Connection at home (do nslookup on your associated domains, switch to Google DNS as your ISP mostly caches DNS way too long >> https://developers.google.com/speed/public-dns/)
13. Sometimes when running the panel and daemon on one server it can help if you add an entry your servers `/etc/hosts` file that redirects your daemons domain to your server itself
14. Same as above, sometimes the reverse way is also needed, so in some cases you need to add an entry to your servers `/etc/hosts` file that points your panels domain to the correct IP.
15. When running daemon and panel on separate VM's on the same adapter, make sure your VM's can connect to each other (promiscuous mode might be needed)
16. Make sure if the daemon is properly installed and the active config (`core.json`) matches your config shown in the nodes settings in the panel

Before contacting the support team, check each possible issue from the list above. If nothing helps and you want to contact us, make sure to provide as much information and output as possible.
**At least** include the output of **9.**.