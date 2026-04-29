
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

The following class models ``ImdbData`` documents:

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/ImdbData.cs
   :language: csharp

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$replaceRoot`` 
  
   .. replacement:: method-name-and-link 

      `ReplaceRoot() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ReplaceRoot.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      replaces each input ``Movie`` document with the ``ImdbData`` document stored
      in its ``Imdb`` property:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start replaceRoot
   :end-before: // end replaceRoot
   :language: csharp
   :dedent: 8

