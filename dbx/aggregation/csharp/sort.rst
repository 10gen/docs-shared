
.. sharedinclude:: dbx/aggregation/csharp/sample-data-movie.rst

.. sharedinclude:: dbx/aggregation/csharp/method-intro.rst

   .. replacement:: stage-name

      ``$sort`` 

   .. replacement:: method-name-and-link 

      `Sort() <{+csharp-api-docs+}/MongoDB.Driver/MongoDB.Driver.PipelineStageDefinitionBuilder.Sort.html>`__

   .. replacement:: stage-specific-info

   .. replacement:: method-description

      sorts the input ``Movie`` documents first in descending order by the ``Year``
      field, then in ascending order by the ``Title`` field:

   .. replacement:: more-method-description

.. literalinclude:: /dbx/aggregation/csharp/code/aggregation/BuildersExamples.cs
   :start-after: // start sort
   :end-before: // end sort
   :language: csharp
   :dedent: 8

