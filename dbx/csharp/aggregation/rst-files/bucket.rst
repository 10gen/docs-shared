
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$bucket``

   .. replacement:: method-name-and-link

      `Bucket() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Bucket.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      groups incoming documents by the value of their ``Runtime`` field, inclusive
      of the lower boundary and exclusive of the upper boundary:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start bucket
   :end-before: // end bucket

To customize the ``$bucket`` operation, pass an
`AggregateBucketOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.AggregateBucketOptions-1.html>`__
object to the ``Bucket()`` method.
The following example performs the same ``$bucket`` operation as the previous example,
but groups all documents with a ``Runtime`` value greater than ``999`` into the
default bucket, named ``"Other"``:

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start bucketOptions
   :end-before: // end bucketOptions
   :language: csharp
   :dedent: 8

