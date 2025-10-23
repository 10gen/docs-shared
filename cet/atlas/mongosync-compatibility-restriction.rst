.. important:: 

   If you are using {+dedicated-clusters+} for your deployment and plan to use 
   live migration or mongosync, do NOT choose :guilabel:`Latest Version With Auto 
   Upgrades`. This option auto upgrades your {+cluster+} to the latest minor release. 
   Some minor releases, such as MongoDB version 8.2, may not be supported by live 
   migration or mongosync. Choose a major version instead to ensure compatibility 
   with these products.