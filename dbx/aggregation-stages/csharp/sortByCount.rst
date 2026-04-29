
.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation-stages/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$sortByCount`` 

   .. replacement:: method-name-and-link 

      `SortByCount() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.SortByCount.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      groups the incoming ``Movie`` documents by the value of their ``Rated`` field,
      and then returns the number of documents in each group:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start sortByCount
   :end-before: // end sortByCount
   :language: csharp
   :dedent: 8

