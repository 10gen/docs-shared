
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$set`` 

   .. replacement:: method-name-and-link 

      `Set() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Set.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      sets the value of the ``LastUpdated`` field in each ``Movie``
      document to the value of ``DateTime.Now``:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start set
   :end-before: // end set
   :language: csharp
   :dedent: 8

