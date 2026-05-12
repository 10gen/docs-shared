The C# examples on this page use the ``sample_mflix`` database
from the :atlas:`Atlas sample datasets </sample-data>`. To learn how to create a
free MongoDB Atlas cluster and load the sample datasets, see
:driver:`Get Started </csharp/current/quick-start/>` in the MongoDB .NET/C#
Driver documentation.

The following ``Movie`` and ``ImdbData`` classes model the documents in the
``sample_mflix.movies`` collection:

.. literalinclude:: /dbx/csharp/aggregation/code/projection/Movie.cs
   :language: csharp

.. literalinclude:: /dbx/csharp/aggregation/code/ImdbData.cs
   :language: csharp

.. sharedinclude:: dbx/csharp/aggregation/convention-pack-note.rst