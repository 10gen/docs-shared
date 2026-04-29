
.. sharedinclude:: dbx/csharp/aggregation/sample-data-movie.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$unwind`` 

   .. replacement:: method-name-and-link 

      `Unwind() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Unwind.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      iterates over the ``Genres`` field in each input ``Movie`` document. For each
      value in the ``Genres`` field, the stage creates a new ``Movie`` document and
      populates its ``Genres`` field with the ``Genres`` value from the input document.

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start unwind
   :end-before: // end unwind
   :language: csharp
   :dedent: 8

You can use an `AggregateUnwindOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.AggregateUnwindOptions-1.html>`__
object to customize the behavior of the ``Unwind()`` method.
The following example performs the same operation as the previous
example, but also includes the following options:

- ``PreserveNullAndEmptyArrays`` ensures that documents that contain an empty
  array in the ``Genres`` field are included in the output.
- The ``IncludeArrayIndex`` option adds a new field named ``Index`` to each output
  document. The value of this field is the array index of the ``Genres`` field's value
  in the input document's ``Genres`` array.

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start unwindPreserve
   :end-before: // end unwindPreserve
   :language: csharp
   :dedent: 8

