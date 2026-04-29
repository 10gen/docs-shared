
.. sharedinclude:: dbx/aggregation/csharp/projection/sample-data-movie.rst

To use the {+csharp-driver-full+} to add a ``$project`` stage to an aggregation
pipeline, call the ``Project()`` method on a ``PipelineDefinition`` object and
pass a ``ProjectionDefinitionBuilder<TDocument>`` object. ``TDocument``
is the class that represents the documents in your collection.

The following sections show the different ways that you can customize the output
documents of the ``$project`` stage.

Include Specific Fields in Output Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To include specific fields when using the .NET/C# driver, call the
``Include()`` method on the projection builder. You can chain ``Include()`` calls
to include multiple fields.

The following code example produces a document that includes only the ``_id``,
``plot``, and ``title`` fields:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start include
   :end-before: // end include

The pipeline returns the following document:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1390f29313caabcd42e8" },
     "plot" : "A group of bandits stage a brazen train hold-up, only to find a
               determined posse hot on their heels.",
     "title" : "The Great Train Robbery"
   }

Exclude Fields from Output Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To exclude a field from the result documents when using the .NET/C# driver, call the
``Exclude()`` method on the projection builder. You can chain ``Exclude()`` calls
to exclude multiple fields.

The following code example produces a document that excludes the ``Type`` field:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start excludeFields
   :end-before: // end excludeFields

By default, result documents always include the ``_id`` field. The following code
example produces a document that excludes the ``_id`` field but includes the ``plot``
and ``title`` fields:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start excludeId
   :end-before: // end excludeId

The pipeline results in the following document:

.. code-block:: javascript
   :copyable: false

   {
     "plot" : "A group of bandits stage a brazen train hold-up, only to find a
               determined posse hot on their heels.",
     "title" : "The Great Train Robbery"
   }

Exclude Fields from Embedded Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To exclude a field in an embedded document when using the .NET/C# driver, call the
``Exclude()`` method on the projection builder and pass the path to the corresponding
class property. You can chain ``Exclude()`` calls to exclude multiple fields.

The following code example produces a document that excludes the ``imdb.id``
and ``type`` fields:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start excludeFieldsEmbedded
   :end-before: // end excludeFieldsEmbedded

The pipeline results in the following output:

.. code-block:: javascript
   :copyable: false

   {
     "plot" : "A group of bandits stage a brazen train hold-up, only to find a
               determined posse hot on their heels.",
     "title" : "The Great Train Robbery",
     ...
     "imdb" : { "rating" : 7.4000000000000004, "votes" : 9847 }
   }

.. note:: Use Strings for Embedded ID Fields

   To project an ID field in an embedded document, specify the field
   name as a string, not a lambda expression.

Conditionally Exclude Fields
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can use the variable :variable:`REMOVE` in aggregation expressions
to conditionally suppress a field:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start excludeFieldsConditional
   :end-before: // end excludeFieldsConditional

.. note:: No Builder for Conditional Exclusion

   The preceding example uses ``BsonDocument`` objects because the .NET/C# driver
   doesn't provide a builder to conditionally exclude fields. Other MongoDB
   language drivers might support this feature. See the
   `MongoDB driver documentation <https://www.mongodb.com/docs/drivers/>`__ for more
   information.

If the sampled document contains the ``imdb.votes`` field, the pipeline
returns a document similar to the following:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1390f29313caabcd42e8" },
     "title" : "The Great Train Robbery",
     "imdb" : { "rating" : 7.4000000000000004, "id" : 439, "votes" : 9847 }
   }

If the document doesn't contain the ``imdb.votes`` field, the pipeline
returns a document similar to the following:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1398f29313caabce94a3" },
     "title" : "This Is Spinal Tap",
    "imdb" : { "rating" : 8.0, "id" : 88258 }
   }

Include Computed Fields
~~~~~~~~~~~~~~~~~~~~~~~

To include computed fields in the result documents when using the .NET/C# driver,
call the ``Expression()`` method on the projection builder and pass an expression
that includes the computed fields. For added type safety, you can define a model
class for the result documents, like the following ``ProjectedMovie`` class:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectedMovie.cs
   :language: csharp

The following code example produces a document that includes multiple computed
fields:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start includeFieldsComputed
   :end-before: // end includeFieldsComputed

The pipeline results in the following document:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1390f29313caabcd42e8" },
     "title" : "The Great Train Robbery",
     "leadActor" : "A.C. Abadie",
     ...
   }

Project New Array Fields
~~~~~~~~~~~~~~~~~~~~~~~~

To project new array fields in the result documents when using the .NET/C# driver,
call the ``Expression()`` method on the projection builder and pass an expression
that includes the new array fields. For added type safety, you can define a model
class for the result documents, like the following ``ProjectedMovie`` class:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectedMovie.cs
   :language: csharp

The following code example produces documents that include a new array field,
``crew``, which contains values from the ``directors`` and ``writers`` fields:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start newArrayFields
   :end-before: // end newArrayFields

The pipeline returns a document similar to the following:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1395f29313caabce2297" },
     "title" : "The Chalk Garden",
     "leadActor" : "Deborah Kerr",
     "crew" : ["Ronald Neame", "John Michael Hayes (screenplay)", "Enid Bagnold (from the play by)"]
   }

If the array specification includes fields that are non-existent in a
document, the pipeline substitutes ``null`` as the value for that
field. For example, the following code example projects the fields ``directors``, ``writers``,
and a non-existent field, ``makeupArtists``, as elements in a new field named ``crew``:

.. literalinclude:: /includes/driver-examples/csharp/projection/ProjectionExamples.cs
   :language: csharp
   :dedent: 8
   :start-after: // start nonExistentNewArrayFields
   :end-before: // end nonExistentNewArrayFields

The pipeline returns a document similar to the following:

.. code-block:: javascript
   :copyable: false

   {
     "_id" : { "$oid" : "573a1399f29313caabced0d9" },
     "crew" : [["Bill Kroyer"], ["Jim Cox (screenplay)", "Diana Young (original stories)"], null]
   }

.. note:: Builders Class Prevents Missing Fields

   The preceding example uses ``BsonDocument`` objects because the .NET/C# driver
   raises a compile-time error if you try to use builders to add a missing field to
   an array. Other MongoDB language drivers might support this feature. See the
   `MongoDB driver documentation <https://www.mongodb.com/docs/drivers/>`__ for more
   information.

