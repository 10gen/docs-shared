.. note:: Adaptive Rate Limiting

   If errors with ``SystemOverloadedError`` or ``RetryableError`` labels are causing
   failures in your application or appearing in your application logs, your
   driver may not be upgraded to a version that supports adaptive rate limiting.
   We recommend upgrading your |driver-name| to version |ivm-compatible-version|
   or later. If you continue to see these errors after upgrading, you may need
   to review your Intelligent Workload Management (IWM) configuration.

   Adaptive rate limiting helps manage server load by dynamically adjusting
   request rates based on current conditions. This feature is available on
   MongoDB 8.3 and later.

   For more information about IWM, see the :atlas:`Reliability, Availability,
   and Workload Management </intelligent-workload-management/>` page or
   :atlas:`Overload Errors
   </overload-errors/?interface=driver&language=|language|>` page in the Atlas
   documentation.