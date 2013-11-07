Dyndnsc - dynamic dns update client
===================================

.. image:: https://travis-ci.org/infothrill/python-dyndnsc.png
    :target: https://travis-ci.org/infothrill/python-dyndnsc

.. image:: https://coveralls.io/repos/infothrill/python-dyndnsc/badge.png
        :target: https://coveralls.io/r/infothrill/python-dyndnsc

.. image:: https://badge.fury.io/py/dyndnsc.png
    :target: http://badge.fury.io/py/dyndnsc

.. image:: https://pypip.in/d/dyndnsc/badge.png
        :target: https://crate.io/packages/dyndnsc/


dyndnsc is both a script to be used directly as well as a re-usable and
hopefully extensible python package for doing updates to dynamic
dns services (http://dyn.com/support/developers/api/).

- updating a dyndns entry is done by a "DynDNS Update Protocol handler"
- detecting IPs, both in DNS or elsewhere is done using IPDetector's
  which all have a detect() method and bookkeeping about changes
- the DynDnsClient uses the Protocol Handler to do the updates and
  the IPDetectors to decide when an update needs to occur

Examples
========

Basic example that should fit most peoples needs:

.. code-block:: bash

    $ dyndnsc  --hostname test.dyndns.com --userid bob --password=fub4r


Are you using `Miredo <http://www.remlab.net/miredo/>`_ and want to assign
a hostname dynamically to your ipv6 tunnel?

.. code-block:: bash

    $ dyndnsc  --hostname test.dyndns.com --userid bob
           --method=Iface,netmask:2001:0000::/32,iface:tun0,family:INET6


Supported services
==================
Currently, this package offers support for

* `dyndns.org <http://dyndns.org/>`_
* `no-ip <https://www.no-ip.com/>`_

Feel free to send pull requests to add more.

Installation
============

.. code-block:: bash

    $ pip install dyndnsc

or, if you want to work using the source tarball:

.. code-block:: bash

    $ python setup.py install
  

Requirements
============
* Python 2.6, 2.7, 3.2 or 3.3