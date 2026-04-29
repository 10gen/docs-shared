
.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$limit`` 
  
   .. replacement:: method-name-and-link 

      `Limit() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Limit.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      limits the number of returned documents to ``10``:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start limit
   :end-before: // end limit
   :language: csharp
   :dedent: 8

