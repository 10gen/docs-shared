
The following ``WeatherMeasurement`` class represents documents in a collection
of weather measurements:

.. literalinclude:: /includes/driver-examples/csharp/aggregation/WeatherMeasurement.cs
   :language: csharp

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$setWindowFields`` 

   .. replacement:: method-name-and-link 

      `SetWindowFields() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.SetWindowFields.html>`__

   .. replacement:: stage-specific-info
   
   .. replacement:: method-description

      uses the ``Rainfall`` and ``Temperature`` fields to compute the accumulated
      rainfall, moving average temperature, median temperature, and 90th percentile
      rainfall over the past month for each locality:

   .. replacement:: more-method-description

.. literalinclude:: /includes/driver-examples/csharp/aggregation/BuildersExamples.cs
   :start-after: // start setWindowFields
   :end-before: // end setWindowFields
   :language: csharp
   :dedent: 8

