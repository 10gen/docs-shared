
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

The following class models ``ImdbData`` documents:

.. literalinclude:: /dbx/csharp/aggregation/code/ImdbData.cs
   :language: csharp

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$replaceWith`` 
  
   .. replacement:: method-name-and-link 

      `ReplaceWith() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ReplaceWith.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      replaces each input ``Movie`` document with the ``ImdbData``
      document stored in its ``Imdb`` property:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start replaceWith
   :end-before: // end replaceWith
   :language: csharp
   :dedent: 8

