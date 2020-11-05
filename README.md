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

To create the Ubuntu droplet `mimix-server-1`, run:

    doadm -DCN mimix-server-1

To destroy the Ubuntu droplet `mimix-server-1`, run:

    doadm -DXN mimix-server-1

To display the list of droplets, run:

    doadm -DL


### <a name="databases">Databases</a>

To create the PostgreSQL database `mimix-db-1`, run:

    doadm -BCN mimix-db-1

To destroy the PostgreSQL database `mimix-db-1`, run:

    doadm -BXN mimix-db-1

To display the list of databases, run:

    doadm -BL


### <a name="firewalls">Firewalls</a>

To create or apply the firewall `mimix-only` to the droplets `mimix-server-1` and `mimix-server-2`,
allowing access from your public IP address and `62.5.13.190` only, on the ports `22`, `80`, and
`443`, run:

    doadm -FCN mimix-only -n mimix-server-1,mimix-server-2 -A -a 62.5.13.190 -p 22,80,443

To delete the firewall `mimix-only` and its association with any droplet, run:

    doadm -FXN mimix-only

To display the list of firewalls, run:

    doadm -FL


### <a name="miscellany">Miscellany</a>

To display usage summary, run:

    doadm --help
