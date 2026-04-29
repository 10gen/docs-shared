
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$changeStreamSplitLargeEvent`` 
  
   .. replacement:: method-name-and-link 

      `ChangeStreamSplitLargeEvent() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ChangeStreamSplitLargeEvent.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      splits events exceeding 16 MB into fragments and returns them sequentially in
      a change stream cursor:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start changeStreamSplitLargeEvent
   :end-before: // end changeStreamSplitLargeEvent
   :language: csharp
   :dedent: 8

