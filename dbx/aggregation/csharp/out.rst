
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$out`` 
  
   .. replacement:: method-name-and-link 

      `Out() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Out.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      writes the results of the pipeline into the ``movies`` collection:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start out
   :end-before: // end out
   :language: csharp
   :dedent: 8

