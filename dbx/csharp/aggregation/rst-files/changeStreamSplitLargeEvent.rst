
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$changeStreamSplitLargeEvent`` 
  
   .. replacement:: method-name-and-link 

      `ChangeStreamSplitLargeEvent() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ChangeStreamSplitLargeEvent.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      splits events exceeding 16 MB into fragments and returns them sequentially in
      a change stream cursor:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start changeStreamSplitLargeEvent
   :end-before: // end changeStreamSplitLargeEvent
   :language: csharp
   :dedent: 8

