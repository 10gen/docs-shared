
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$count`` 

   .. replacement:: method-name-and-link 

      `Count() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Count.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      counts the number of input documents and returns a document with the count as
      its value:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start count
   :end-before: // end count
   :language: csharp
   :dedent: 8

