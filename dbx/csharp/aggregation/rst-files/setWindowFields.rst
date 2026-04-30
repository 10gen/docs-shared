
The following ``WeatherMeasurement`` class represents documents in a collection
of weather measurements:

.. literalinclude:: /dbx/csharp/aggregation/code/WeatherMeasurement.cs
   :language: csharp

.. sharedinclude:: dbx/csharp/aggregation/method-intro.rst

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

.. literalinclude:: /dbx/csharp/aggregation/code/BuildersExamples.cs
   :start-after: // start setWindowFields
   :end-before: // end setWindowFields
   :language: csharp
   :dedent: 8

