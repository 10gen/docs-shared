
.. sharedinclude:: dbx/csharp/aggregation/meta/sample-data-movie.rst

To include the text search score by using the .NET/C# driver, call the
`MetaTextScore() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.ProjectionDefinitionBuilder-1.MetaTextScore.html>`__
method on the projection builder.

First, run the following code to create a text index on the ``Title`` field:

.. literalinclude:: /dbx/csharp/aggregation/code/meta/MetaExamples.cs
   :start-after: // start createIndex
   :end-before: // end createIndex
   :language: csharp
   :dedent: 8

Then, add the following code to your application. The code performs a text search
for the term ``"future"`` and uses the ``MetaTextScore()`` method to include the
score assigned to each matching document. The code then sorts the results in
descending order by their text score and returns the document with the highest score.

.. literalinclude:: /dbx/csharp/aggregation/code/meta/MetaExamples.cs
   :start-after: // start metaTextScore
   :end-before: // end metaTextScore
   :language: csharp
   :dedent: 8

The preceding operation returns the following document:

.. code-block:: json

   {
     "_id": {
       "$oid": "573a1398f29313caabceb500"
     },
     "plot": "After visiting 2015, Marty McFly must repeat his visit to 1955 to
      prevent disastrous changes to 1985... without interfering with his first trip.",
     "title": "Back to the Future Part II",
     "score": 1.59375
   } 
