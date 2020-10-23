docmd
=====


<a name="toc">Table of contents</a>
-----------------------------------

- [Overview](#overview)
- [Dependencies](#dependencies)
- [Usage](#usage)
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

### <a name="init">Initial usage</a>

Before using this script, you must first authenticate with DigitalOcean. To do so, run:

    doctl auth init


### <a name="droplets">Droplets</a>

To create the Ubuntu droplet `mimix-server-1`, run:

    docmd -OCn mimix-server-1

To delete the Ubuntu droplet `mimix-server-1`, run:

    docmd -ODn mimix-server-1

To list all droplets, run:

    docmd -OL


### <a name="databases">Databases</a>

To create the PostgreSQL database `mimix-db-1`, run:

    docmd -BCn mimix-db-1

To delete the PostgreSQL database `mimix-db-1`, run:

    docmd -BDn mimix-db-1

To list all databases, run:

    docmd -BL


### <a name="firewalls">Firewalls</a>

To create or apply the firewall `mimix-only` to the droplets `mimix-server-1` and `mimix-server-2`,
allowing access from your public IP address and `62.5.13.190` only, on the ports `22`, `80`, and
`443`, run:

    docmd -FCn mimix-only -N mimix-server-1,mimix-server-2 -A -a 62.5.13.190 -p 22,80,443

To delete the firewall `mimix-only` and its association with any droplet, run:

    docmd -FDn mimix-only

To display the list of firewalls, run:

    docmd -FL


### <a name="miscellany">Miscellany</a>

To display usage summary, run:

    docmd --help
