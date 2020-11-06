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

To create the Ubuntu droplet `droplet-1`, run:

    doadm -DCN droplet-1

To destroy the Ubuntu droplet `droplet-1`, run:

    doadm -DXN droplet-1

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

To create or apply the firewall `mimix` to the droplets `droplet-1` and `droplet-2`,
allowing access from your public IP address and `62.5.13.190` only, on the ports `22`, `80`, and
`443`, run:

    doadm -FCN mimix -a droplet-1,droplet-2 -SA 62.5.13.190 -P 22,80,443

To remove `droplet-2` from the firewall `mimix`, run:

    doadm -FCN mimix -x droplet-2

To delete the firewall `mimix` and its association with any droplet, run:

    doadm -FXN mimix

To display the list of firewalls, run:

    doadm -FL


### <a name="miscellany">Miscellany</a>

To display usage summary, run:

    doadm --help
