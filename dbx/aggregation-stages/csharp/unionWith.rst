
.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$unionWith`` 

   .. replacement:: method-name-and-link 

      `UnionWith() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.UnionWith.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      combines the incoming documents from the ``sample_mflix.movies`` collection
      with the ``Movie`` documents in the ``sample_mflix.Movies`` collection:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start unionWith
   :end-before: // end unionWith
   :language: csharp
   :dedent: 8

