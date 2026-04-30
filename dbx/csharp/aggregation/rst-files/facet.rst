
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$facet`` 
  
   .. replacement:: method-name-and-link 

      `Facet() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Facet.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      executes two parallel aggregations. The first aggregation distributes incoming
      documents into five groups by the value of their ``Runtime`` field. The second
      aggregation counts each value in the ``Rated`` field and returns the
      count for each value, limited to the top five values.

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start facet
   :end-before: // end facet
   :language: csharp
   :dedent: 8

