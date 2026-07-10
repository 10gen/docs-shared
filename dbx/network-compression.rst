Overview
--------

MongoDB drivers can compress the messages sent to and received
from {+mdb-server+}. This reduces the amount of data
transferred for each operation. Compression can improve performance
over constrained networks and lower the data transfer costs
associated with running MongoDB Atlas.

Compression operates at the wire protocol level, so it applies to
every operation that your application performs. If you specify more
than one algorithm, the driver uses the first algorithm in your list
that {+mdb-server+} also supports.

Compression Algorithms
~~~~~~~~~~~~~~~~~~~~~~

MongoDB drivers support the following compression algorithms:

- `Snappy <https://google.github.io/snappy/>`__
- `Zlib <https://zlib.net/>`__
- `Zstandard <https://facebook.github.io/zstd/>`__

Network Compression Benefits
----------------------------

MongoDB Atlas charges for data transferred across cloud regions, cloud
providers, and between your infrastructure and MongoDB Atlas. Network
compression reduces the amount of data that your application sends
and receives, which can lower these data transfer costs. To learn
more about pricing, see :atlas:`Data Transfer Costs
</billing/data-transfer-costs/>`.

Network compression also has productivity benefits. Compressed
messages take less time to transfer across the network, which can
improve your application's response times. Compression also
reduces the bandwidth that your MongoDB traffic uses, which leaves
more bandwidth available for other applications on the same network.

When you choose a compression algorithm, consider the following
guidelines:

- Use **Zstandard** for a balance of compression efficiency and resource
  usage. Zstandard is a good default choice for most applications.
- Use **Snappy** for latency-sensitive applications that require
  minimal computational overhead.
- Use **Zlib** for broad compatibility across MongoDB drivers and
  environments.

.. tip:: Monitor CPU Usage

   Compression trades network bandwidth for CPU usage. After you
   enable network compression, monitor your application's
   CPU utilization to confirm that the trade-off benefits your workload.
   To learn more about these trade-offs, see the
   :website:`CPU Utilization and Network Compression in MongoDB
   </company/blog/technical/practical-guide-cpu-utilization-network-compression-in-mongodb/>`
   blog post.