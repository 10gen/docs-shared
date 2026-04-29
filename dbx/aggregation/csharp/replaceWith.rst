
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

The following class models ``ImdbData`` documents:

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/ImdbData.cs
   :language: csharp

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$replaceWith`` 
  
   .. replacement:: method-name-and-link 

      `ReplaceWith() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ReplaceWith.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      replaces each input ``Movie`` document with the ``ImdbData``
      document stored in its ``Imdb`` property:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start replaceWith
   :end-before: // end replaceWith
   :language: csharp
   :dedent: 8

