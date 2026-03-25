.. note::

   If you find errors with ``SystemOverloadedError`` or ``RetryableError``
   labels in your application logs, you can consider changes to your retry
   settings. One option is to enable adaptive rate limiting on your server.
   Adaptive rate limiting helps manage server load by dynamically adjusting
   request rates based on current conditions, while also managing client-side
   retry requests to mitigate errors. This feature is available on MongoDB 8.3
   and supported by the |driver-name| version |ivm-compatible-version|.
   
   For more information, see the :atlas:`Reliability, Availability, and Workload
   Management </intelligent-workload-management/>` page or :atlas:`Overload
   Errors </overload-errors/?interface=driver&language=|language|>` page in
   the Atlas documentation.