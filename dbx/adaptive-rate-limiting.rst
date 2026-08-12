.. note:: Adaptive Rate Limiting

   If errors with ``SystemOverloadedError`` or ``RetryableError`` labels are causing
   failures in your application or appearing in your application logs, Overload
   Protection may be active on your cluster and your driver may not be upgraded to
   a version that supports it. We recommend upgrading your |driver-name| to
   version |ivm-compatible-version| or later. If you continue to see these
   errors after upgrading, you can address them through server-side changes,
   such as reviewing your Overload Protection configuration,
   or through application-side changes, such as implementing custom error
   handling or client-side request throttling. Depending on your situation,
   application-side changes may be preferable or necessary. 

   Overload Protection is a feature of Intelligent Workload Management (IWM),
   and helps manage server load by rejecting or terminating excess work during
   sustained overload. This feature is available on MongoDB 9.0 and later.
   
   For more information about IWM or handling overload errors, see the :atlas:`Intelligent Workload
   Management </intelligent-workload-management/>` page or :atlas:`Overload
   Errors </overload-errors/?interface=driver&language=|language|>` page in the
   Atlas documentation.