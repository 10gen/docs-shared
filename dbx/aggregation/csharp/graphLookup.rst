
A collection named ``employees`` has the following documents:

.. code-block:: javascript

   { _id: 1, name: "Dev" },
   { _id: 2, name: "Eliot", reportsTo: "Dev" },
   { _id: 3, name: "Ron", reportsTo: "Eliot" },
   { _id: 4, name: "Andrew", reportsTo: "Eliot" },
   { _id: 5, name: "Asya", reportsTo: "Ron" },
   { _id: 6, name: "Dan", reportsTo: "Andrew" }

The following ``Employee`` class models documents in the ``employees`` collection:

.. literalinclude:: /includes/driver-examples/csharp/aggregation/Employee.cs
   :language: csharp

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$graphLookup`` 
  
   .. replacement:: method-name-and-link 

      `GraphLookup() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.GraphLookup.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      recursively matches on the ``ReportsTo`` and ``Name`` fields in the ``employees``
      collection, returning the reporting hierarchy for each person:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start graphLookupBasic
   :end-before: // end graphLookupBasic
   :language: csharp
   :dedent: 8

You can use an `AggregateGraphLookupOptions <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.AggregateGraphLookupOptions-3.html>`__
object to specify the depth to recurse and name of the depth field. The following
code example performs the same ``$graphLookup`` operation as the previous example,
but specifies a maximum recursion depth of ``1``:

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start graphLookupDepth
   :end-before: // end graphLookupDepth
   :language: csharp
   :dedent: 8

You can also use an ``AggregateGraphLookupOptions`` object to specify a filter that documents
must match in order for MongoDB to include them in your search. The following code
example performs the same ``$graphLookup`` operation as the previous examples, but
includes only ``Employee`` documents where the ``Hobbies`` field contains ``"golf"``:

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start graphLookupMatch
   :end-before: // end graphLookupMatch
   :language: csharp
   :dedent: 8

