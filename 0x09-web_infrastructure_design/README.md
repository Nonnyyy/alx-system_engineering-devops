# Web infrastructure design

# The Tasks Were:
- Simple web stack
##  Description

This is a simple web infrastructure that hosts a website that is reachable via `www.foobar.com`. There are no firewalls or SSL certificates for protecting the server's network. Each component (database, application server) has to share the resources (CPU, RAM, and SSD) provided by the server.

- Distributed Web Infrastructure
## Description

This is a distributed web infrastructure that atttempts to reduce the traffic to the primary server by distributing some of the load to a replica server with the aid of a server responsible for balancing the load between the two servers (primary and replica).

- Secured and Monitored Web Infrastructure
## Description

This is a 3-server web infrastructure that is secured, monitored, and serves encrypted traffic.

- Scaled Up Web Infrastructure
## Description

This web infrastructure is a scaled up version of the infrastructure described Secured and Monitored Web Infrastructure. In this version, all SPOFs have been removed and each of the major components (web server, application server, and database servers) have been moved to separate GNU/Linux servers. The SSL protection isn't terminated at the load-balancer and each server's network is protected with a firewall and they're also monitored.

Author
Lucy Migwi.
