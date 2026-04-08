.. note:: Adaptive Rate Limiting

   If you see ``SystemOverloadedError`` or ``RetryableError`` errors in your
   application logs or failures in your application, your driver may not be
   upgraded to a version that supports adaptive rate limiting. We recommend
   upgrading your |driver-name| to version |ivm-compatible-version| or later.

   Adaptive rate limiting helps manage server load by dynamically adjusting
   request rates based on current conditions. This feature is available on
   MongoDB 8.3 and later.

   For more information, see the :atlas:`Reliability, Availability, and Workload
   Management </intelligent-workload-management/>` page or :atlas:`Overload
   Errors </overload-errors/?interface=driver&language=|language|>` page in
   the Atlas documentation.