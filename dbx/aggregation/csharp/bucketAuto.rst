
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$bucketAuto`` 
  
   .. replacement:: method-name-and-link 

      `BucketAuto() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.BucketAuto.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      evenly distributes documents into five buckets by the value of their ``Runtime``
      field:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start bucketAuto
   :end-before: // end bucketAuto
   :language: csharp
   :dedent: 8

You can use an `AggregateBucketAutoOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.AggregateBucketAutoOptions.html>`__
object to specify a :wikipedia:`preferred number <Preferred_number>`
-based scheme to set boundary values. 
The following example performs the same ``$bucketAuto`` operation as the previous
example, but also sets the bucket boundaries at powers of 2:

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start bucketAutoOptions
   :end-before: // end bucketAutoOptions
   :language: csharp
   :dedent: 8 

