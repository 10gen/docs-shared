
.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$changeStream`` 
  
   .. replacement:: method-name-and-link 

      `ChangeStream() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.ChangeStream.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      returns a change stream cursor:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start changeStream
   :end-before: // end changeStream
   :language: csharp
   :dedent: 8

You can use a `ChangeStreamStageOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.ChangeStreamStageOptions.html>`__
object to customize the behavior of the change stream.
The following example performs the same ``$changeStream`` operation as the previous
example, but specifies the following options:

- The ``FullDocument`` option specifies that change notifications don't include a
  copy of the full document when modified by update operations.
- The ``StartAtOperationTime`` option specifies the logical starting point for the
  change stream.

.. literalinclude:: /dbx/csharp/aggregation/code/aggregation/BuildersExamples.cs
   :start-after: // start changeStreamOptions
   :end-before: // end changeStreamOptions
   :language: csharp
   :dedent: 8 

.. note:: Prefer the ``Watch()`` Method

   Where possible, use the ``IMongoCollection<TDocument>.Watch()`` method instead
   of this aggregation stage. Use the ``ChangeStream()`` method
   only if subsequent stages project away the resume token (``_id``) or if you don't
   want the resulting cursor to automatically resume.

