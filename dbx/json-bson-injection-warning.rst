.. warning:: Validate Untrusted Input Before Converting JSON to BSON

   If you convert a JSON string to BSON and use the resulting BSON in a
   query, update, or command, an attacker can inject operators or
   unexpected field values that change the meaning of the operation.
   This risk is greatest when the JSON originates from a user, an
   API request, or another untrusted source.

   To learn more about validating input before conversion, see
   :ref:`client-libraries-security-best-practices`.

.. TODO: DOCSP-61609 must define a page with the label
   client-libraries-security-best-practices before this ref resolves.
   Update the label here if DOCSP-61609 ships with a different one.
