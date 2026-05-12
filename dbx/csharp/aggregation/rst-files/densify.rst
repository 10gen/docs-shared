
.. sharedinclude:: dbx/csharp/aggregation/sample-data-weather.rst

The ``sample_weatherdata.data`` collection contains the following documents,
which contain measurements for the same ``position`` field, one hour apart:

.. code-block:: none
   :copyable: false

   Document{{ _id=5553a..., position=Document{{type=Point, coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 08:00:00 EST 1984, ... }}
   Document{{ _id=5553b..., position=Document{{type=Point, coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 09:00:00 EST 1984, ... }}

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$densify`` 
  
   .. replacement:: method-name-and-link 

      `Densify() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Densify.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      adds a document at every 15-minute interval between the previous two documents.
      The code then groups these documents by the values of their
      ``Position.Coordinates`` field.

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start densify
   :end-before: // end densify
   :language: csharp
   :dedent: 8

The previous aggregation stage generates the following highlighted documents in the
collection:

.. code-block:: none
   :emphasize-lines: 2-4
   :copyable: false

   Document{{ _id=5553a..., position=Document{{type=Point, coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 08:00:00 EST 1984, ... }}
   Document{{ position=Document{{coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 08:15:00 EST 1984 }}
   Document{{ position=Document{{coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 08:30:00 EST 1984 }}
   Document{{ position=Document{{coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 08:45:00 EST 1984 }}
   Document{{ _id=5553b..., position=Document{{type=Point, coordinates=[-47.9, 47.6]}}, ts=Mon Mar 05 09:00:00 EST 1984, ... }}

