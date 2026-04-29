
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$group``

   .. replacement:: method-name-and-link

      `Group() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Group.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      groups documents by the value of their ``Rated`` field. Each group's rating
      is shown in a field named ``Rating`` in each output document. Each output
      document also contains fields named ``TotalRuntime``, ``MedianRuntime``, and
      ``NinetiethPercentileRuntime``, which store the total, median, and 90th
      percentile runtime values for movies in each group.
      
   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start group
   :end-before: // end group
   :language: csharp
   :dedent: 8

