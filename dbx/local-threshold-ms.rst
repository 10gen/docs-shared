When connecting to a replica set with a non-primary read preference,
the driver reads from the nearest eligible replica set member within
the latency window. When connecting to a sharded cluster, the driver
selects from all reachable ``mongos`` instances within the latency
window.

By default, the driver uses only those servers whose ping times are
within 15 milliseconds of the nearest server.

For example, suppose your replica set has five members and the
nearest member has a ping time of 5 milliseconds. With the default
``localThresholdMS`` of 15 milliseconds, only members with a ping
time of 20 milliseconds or less are within the latency window:

.. list-table::
   :header-rows: 1
   :widths: 25 25 25 25

   * - Host
     - Type
     - Ping Time
     - Within Latency Window
   * - ``host1``
     - Primary
     - 5ms
     - Yes
   * - ``host2``
     - Secondary
     - 9ms
     - Yes
   * - ``host3``
     - Secondary
     - 13ms
     - Yes
   * - ``host4``
     - Secondary
     - 24ms
     - No
   * - ``host5``
     - Secondary
     - 42ms
     - No
