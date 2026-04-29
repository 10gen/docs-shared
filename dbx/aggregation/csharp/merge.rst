
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$merge``

   .. replacement:: method-name-and-link

      `Merge() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Merge.html>`__

   .. replacement:: stage-specific-info

      When you call the ``Merge()`` method, you must pass an instance of the
      `MergeStageOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.MergeStageOptions-1.html>`__
      class. This object lets you specify options for the ``$merge`` stage, such as
      how to handle matching documents.

   .. replacement:: method-description

      merges the documents in the pipeline into the ``movies`` collection. The
      ``MergeStageOptions`` object specifies the following options:

   .. replacement:: more-method-description
   
      - The ``OnFieldNames`` option specifies that the operation should use the ``"id"``
        and ``"title"`` fields to find matching documents in the source collection and the
        ``movies`` collection.
      - The ``WhenMatched`` option specifies that if a document in the source collection matches a
        document in the ``movies`` collection, it should replace the document in the
        ``movies`` collection.
      - The ``WhenNotMatched`` option specifies that if a document in the source collection does
        not match a document in the ``movies`` collection, it should be inserted into the
        ``movies`` collection.

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start merge
   :end-before: // end merge
   :language: csharp
   :dedent: 8

