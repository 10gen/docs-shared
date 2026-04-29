
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

The following ``Comment`` class models the documents in the ``sample_mflix.comments``
collection:

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/Comment.cs
   :language: csharp

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$lookup``

   .. replacement:: method-name-and-link

      `Lookup() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Lookup.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      performs a left outer join between the ``movies`` and ``comments`` collections.
      The code joins the ``Id`` field from each ``Movie`` document to the ``MovieId``
      field in the ``Comment`` documents. The comments for each movie are stored in a field
      named ``Comments`` in each ``Movie`` document.

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start lookup
   :end-before: // end lookup
   :language: csharp
   :dedent: 8

