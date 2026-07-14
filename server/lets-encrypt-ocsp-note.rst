.. note:: Let's Encrypt OCSP Deprecation

   `Let's Encrypt has ended OCSP support
   <https://letsencrypt.org/2024/12/05/ending-ocsp/>`__ for newer
   certificates. New certificates issued by Let's Encrypt
   might not include an OCSP responder URL. OCSP revocation checking
   occurs only when a certificate contains an OCSP URI, so a missing
   OCSP URL is expected and doesn't necessarily indicate a problem with
   your MongoDB deployment.
