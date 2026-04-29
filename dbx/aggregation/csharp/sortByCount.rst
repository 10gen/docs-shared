
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$sortByCount`` 

   .. replacement:: method-name-and-link 

      `SortByCount() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.SortByCount.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      groups the incoming ``Movie`` documents by the value of their ``Rated`` field,
      and then returns the number of documents in each group:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start sortByCount
   :end-before: // end sortByCount
   :language: csharp
   :dedent: 8

