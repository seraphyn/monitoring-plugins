Check nodebb-stats
==================

Overview
--------

Gets some statistics from the ``/api/admin/settings/post`` and ``/api/admin/manage/users`` endpoints for debugging purposes.

The Plugin uses the Read API and Bearer Authentication. You need to issue a bearer token of type "user" in the NodeBB admin panel in order to grant access to the API. In NodeBB, a user token is associated with a specific uid, and all calls are made in the name of that user.

* Settings > API Access > Create Token > Specify your User ID and Description (for example "Linuxfabrik API Token").

Hints:

* NodeBB Read API: https://docs.nodebb.org/api/read/
* Requires NodeBB v1.14.4+.


Fact Sheet
----------

.. csv-table::
    :widths: 30, 70
    
    "Check Plugin Download",                "https://github.com/Linuxfabrik/monitoring-plugins/tree/main/check-plugins/nodebb-stats"
    "Check Interval Recommendation",        "Once a minute"
    "Can be called without parameters",     "No"
    "Available for",                        "Python 2, Python 3, Windows"
    "Requirements",                         "NodeBB v1.14.4+"


Help
----

.. code-block:: text

    usage: nodebb-stats [-h] [-V] [--insecure] [--test TEST] [--timeout TIMEOUT]
                        [-p TOKEN] [--url URL]

    Gets some statistics from the /api/admin/settings/post and
    /api/admin/manage/users endpoints for debugging purposes.

    optional arguments:
      -h, --help            show this help message and exit
      -V, --version         show program's version number and exit
      --insecure            This option explicitly allows to perform "insecure"
                            SSL connections. Default: False
      --test TEST           For unit tests. Needs "path-to-stdout-file,path-to-
                            stderr-file,expected-retc".
      --timeout TIMEOUT     Network timeout in seconds. Default: 3 (seconds)
      -p TOKEN, --token TOKEN
                            NodeBB API Bearer token.
      --url URL             NodeBB API URL. Default: http://localhost:4567/forum


Usage Examples
--------------

.. code-block:: bash

    ./nodebb-stats --token bc68eed3-4cff-4a6e-8372-3b41dfa67635

Output:

.. code-block:: text

    185 users, Last user: Linuxfabrik <info at linuxfabrik dot ch> (online 0.00s ago), 38 groups, Newest group: "The Garden" (private) with 3 members (created 2M 3W ago)


States
------

* Always returns OK.


Perfdata / Metrics
------------------

.. csv-table::
    :widths: 25, 15, 60
    :header-rows: 1
    
    Name,                                       Type,               Description
    groups,                                     Number,             Number of groups
    users,                                      Number,             Number of users


Credits, License
----------------

* Authors: `Linuxfabrik GmbH, Zurich <https://www.linuxfabrik.ch>`_
* License: The Unlicense, see `LICENSE file <https://unlicense.org/>`_.
