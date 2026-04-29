
.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$skip`` 

   .. replacement:: method-name-and-link 

      `Skip() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Skip.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      skips the first five documents in the input and passes
      the remaining documents to the next stage in the pipeline:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start skip
   :end-before: // end skip
   :language: csharp
   :dedent: 8

