.. note::

   You may find errors with ``SystemOverloadedError`` or ``RetryableError`` in
   your application logs if your have not updated your |driver-name| to version
   |ivm-compatible-version|. These errors indicate that the server is under
   heavy load and is applying adaptive rate limiting to manage resources
   effectively. To mitigate these errors, consider updating your |driver-name|
   to version |ivm-compatible-version|.
   
   For more information, see the :atlas:`Reliability, Availability, and Workload
   Management </intelligent-workload-management/>` page or :atlas:`Overload
   Errors </overload-errors/?interface=driver&language=|language|>` page in
   the Atlas documentation.