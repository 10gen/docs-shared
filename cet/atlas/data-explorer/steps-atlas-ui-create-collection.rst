.. procedure::
   :style: normal

   .. step:: In |service|, go to the :guilabel:`Data Explorer` page for your project

      a. If it's not already displayed, select the 
         organization that contains your project from the
         |ui-org-menu| in the navigation bar.

      #. If it's not already displayed, select your project 
         from the :guilabel:`Projects` menu in the navigation bar.

      #. In the sidebar, click :guilabel:`Data Explorer` under 
         the :guilabel:`Database` heading.

         The `Data Explorer <https://cloud.mongodb.com/go?l=https%3A%2F%2Fcloud.mongodb.com%2Fv2%2F%3Cproject%3E%23%2Fmetrics%2FreplicaSet%2F%3Creplset%3E%2Fexplorer>`__ displays.

   .. step:: Open the :guilabel:`Create Collection` dialog box.
      
      Select or hover over the database, and click the :icon-lg:`Plus` icon to 
      open the :guilabel:`Create Collection` dialog box.
      
   .. step:: Enter the :guilabel:`Collection Name`.

      In the :guilabel:`Create Collection` dialog box, enter the name of 
      the collection you want to create. 

      |service| also provides :guilabel:`Additional preferences`. You can choose 
      from the following options: 

      - :ref:`Create a Clustered Collection <atlas-ui-clustered-collection>`
      - :ref:`Create a Collection with Collation <atlas-ui-collation-collection>`

      .. important::
      
         Don't include :ref:`sensitive information <sensitive-info>` in 
         your collection name.
      
      For more information on MongoDB collection names, see
      :ref:`restrictions-on-db-names`.
      
   .. step:: Optional. Specify a time series collection.

      Select whether the collection is a 
      :manual:`time series collection </core/timeseries-collections>`. 
      If you select to create a time series collection, specify the time
      field and granularity. You can optionally specify the meta field and
      the time for old data in the collection to expire.
      
   .. step:: Click :guilabel:`Create Collection`.
      
      Upon successful creation, the collection appears underneath the
      database in the :guilabel:`Connections` sidebar.  
