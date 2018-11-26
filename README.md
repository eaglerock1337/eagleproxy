Eagleworld.net NGINX-based Web Server Reverse Proxy
===================================================

The purpose of this server is to accept all incoming traffic on
port 80 and direct it to all Eagleworld.net web servers. The list
of servers either already implemented or planned to be are located
in the ports.txt file in this repo.

This deployment supports a canary deployment which allows testing
the proxy as well as all other web-based services using alternate
ports by the following spec:

  Port 80 -     Production Web Proxy
  Port 81 -     Staging Web Proxy (Canary Deployments)
  Port 8081+ -  Production Websites
  Port 8181+ -  Staging Websites

  NOTE: Port 8080 is reserved for Jenkins in Eagleworld.net, so
  the web cluster does not use port 8080 or 8180 for this reason.

This proxy is designed to be pushed out via Jenkins using a
Multibranch Pipeline. For fully automated deployments, a developer
GitHub token should be created with repo and repo:hook permissions
to allow for GitHub SCM Polling for automatic build kickoff.
