
.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$sample`` 

   .. replacement:: method-name-and-link 

      `Sample() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Sample.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      returns five random documents from the input collection:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start sample
   :end-before: // end sample
   :language: csharp
   :dedent: 8

