
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$match`` 
  
   .. replacement:: method-name-and-link 

      `Match() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Match.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      matches all ``Movie`` documents where the ``Title`` field is equal to
      ``"The Shawshank Redemption"``:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start match
   :end-before: // end match
   :language: csharp
   :dedent: 8

