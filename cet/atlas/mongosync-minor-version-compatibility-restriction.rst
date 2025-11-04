.. important:: 

   If you are using {+dedicated-clusters+} for your deployment and plan to use 
   Live Migration in the {+atlas-ui+} or standalone |mongosync|, 
   do NOT choose :guilabel:`Latest Version With Auto Upgrades`. 
   This option auto upgrades your {+cluster+} to the latest minor release. 
   Some minor releases, such as MongoDB version 8.2, may not support Live 
   Migration or Mongosync. When upgrading, choose a major version to 
   :ref:`upgrade <major-version-upgrade-procedure>` to instead. 
   This ensures compatibility with Live Migration and Mongosync.