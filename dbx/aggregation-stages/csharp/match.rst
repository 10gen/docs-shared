
.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$match`` 
  
   .. replacement:: method-name-and-link 

      `Match() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Match.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      matches all ``Movie`` documents where the ``Title`` field is equal to
      ``"The Shawshank Redemption"``:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start match
   :end-before: // end match
   :language: csharp
   :dedent: 8

