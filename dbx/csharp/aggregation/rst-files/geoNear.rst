
.. sharedinclude:: dbx/csharp/aggregation/sample-data-theaters.rst

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

   .. replacement:: stage-name

      ``$geoNear`` 
  
   .. replacement:: method-name-and-link 

      `GeoNear() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.GeoNear.html>`__

   .. replacement:: stage-specific-info

      This method is available only in {+csharp-driver-full+} v3.4
      and later.

      Maximum Distance
      ~~~~~~~~~~~~~~~~

   .. replacement:: method-description

      returns documents in an ``8000`` meter radius of the specified
      point, in order of ascending distance. The code includes a
      ``Query`` parameter that only matches documents in which the
      value of the ``location.address.state`` field is ``"NJ"``.
      The code also stores the calculated distance in the
      ``distance`` field of the output documents.

   .. replacement:: more-method-description

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start geoNear
   :end-before: // end geoNear
   :language: csharp
   :dedent: 8

Minimum Distance
~~~~~~~~~~~~~~~~

The following example returns the first ``4`` matching documents
outside of an ``8000`` meter radius of the specified point, in
order of ascending distance. The code includes a ``Query``
parameter that only matches documents in which the value of the
``location.address.state`` field is ``"NJ"``. The code also stores
the calculated distance in the ``distance`` field of the output
documents.

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start geoNear min
   :end-before: // end geoNear min
   :language: csharp
   :dedent: 8

