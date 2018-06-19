hxpro.munin
===========

Munin is a networked resource monitoring tool that can help analyze resource trends and
"what just happened to kill our performance?" problems. It is designed to be very plug and play.
A default installation provides a lot of graphs with almost no work.

Requirements
------------


Role Variables
--------------

    # used in nginx configuration
    munin_server_name: munin.example.com

    # ansible group with munin-nodes
    munin_node_group: all

    # allow access to munin gui from list of cidrs
    munin_allow_from:
      - 127.0.0.1/32

    # Optional (CN = munin_server_name)
    munin_ssl_cert: /path/to/ssl/cert.pem
    munin_ssl_cert_key: /path/to/ssl/key.pem


Dependencies
------------

 - hxpro.nginx

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: hxpro.munin
           munin_server_name: munin.localdomain
           munin_node_group: all
           munin_allow_from:
             - 192.168.0.0/24

License
-------

WTFPL

Author Information
------------------

Matěj Koudelka <matej@hxpro.cz>
