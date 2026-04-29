
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$count`` 

   .. replacement:: method-name-and-link 

      `Count() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Count.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      counts the number of input documents and returns a document with the count as
      its value:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start count
   :end-before: // end count
   :language: csharp
   :dedent: 8

