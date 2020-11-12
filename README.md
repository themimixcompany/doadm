doadm
=====


<a name="toc">Table of contents</a>
-----------------------------------

- [Overview](#overview)
- [Dependencies](#dependencies)
- [Usage](#usage)
  + [Initialization](#init)
  + [Droplets](#droplets)
  + [Databases](#databases)
  + [Firewalls](#firewalls)
  + [Miscellany](#miscellany)


<a name="overview">Overview</a>
-------------------------------

Scripts for managing DigitalOcean droplets, databases, and firewalls.


<a name="dependencies">Dependencies</a>
---------------------------------------

- doctl
- dig


<a name="usage">Usage</a>
-------------------------

### <a name="init">Initialization</a>

Before using this script, you must first authenticate with DigitalOcean. To do so, run:

    doadm -I


### <a name="droplets">Droplets</a>

To create a droplet with the name `droplet-1`, run:

    doadm -CDN droplet-1

To expunge the droplet with the name `droplet-1`, run:

    doadm -XDN droplet-1

To display the list of droplets, run:

    doadm -lD


### <a name="databases">Databases</a>

To create the PostgreSQL database `mimix-db-1`, run:

    doadm -CBN mimix-db-1

To destroy the PostgreSQL database `mimix-db-1`, run:

    doadm -XBN mimix-db-1

To display the list of databases, run:

    doadm -lB


### <a name="firewalls">Firewalls</a>

To create or apply the firewall `mimix` to the droplets `droplet-1` and `droplet-2`,
allowing access from your public IP address and `62.5.13.190` only, on the ports `22`, `80`, and
`443`, run:

    doadm -CFN mimix -a droplet-1,droplet-2 -SA 62.5.13.190 -P 22,80,443

To expel `droplet-2` from the firewall `mimix`, run:

    doadm -CFN mimix -x droplet-2

To expunge the firewall `mimix` and its association with any droplet, run:

    doadm -XXN mimix

To display the list of firewalls, run:

    doadm -lF


### <a name="miscellany">Miscellany</a>

To display usage summary, run:

    doadm --help
