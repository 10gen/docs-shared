.. step:: Configure your SAML integration.

   .. procedure::
      :style: connected

      .. step:: In your |idp-provider| account, return to the page
	 for your SAML application and ensure the :guilabel:`General`
	 tab is selected.

      .. step:: In the :guilabel:`SAML Settings` pane, click
	 :guilabel:`Edit`. 

	 On the :guilabel:`General Settings` page, click
	 :guilabel:`Next`.

      .. step:: On the :guilabel:`Configure SAML` screen, enter the
	 following information:

	 .. list-table::
	    :widths: 20 40
	    :header-rows: 1

	    * - Okta Data Field
	      - Value

	    * - :guilabel:`Single sign on URL`
	      - :guilabel:`Assertion Consumer Service URL` from the
		|service| FMC.

		Checkboxes:

		- Check :guilabel:`Use this for Recipient URL and Destination URL`.
		- Clear :guilabel:`Allow this app to request other SSO URLs`.

	    * - :guilabel:`Audience URI (SP Entity ID)`
	      - :guilabel:`Audience URI` from the |service| FMC.

	    * - :guilabel:`Default RelayState`
	      - .. include:: /includes/optional-idp-relay-state-step.rst

	    * - :guilabel:`Name ID format`
	      - Unspecified

	    * - :guilabel:`Application username`
	      - Email

	    * - :guilabel:`Update application username on`
	      - Create and update

      .. step:: Click the :guilabel:`Click Show Advanced Settings` link in the
	 Okta configuration page and ensure that the following values are
	 set:

	 .. list-table::
	    :widths: 20 40
	    :header-rows: 1

	    * - Okta Data Field
	      - Value

	    * - :guilabel:`Response`
	      - ``Signed``

	    * - :guilabel:`Assertion Signature`
	      - ``Signed``

	    * - :guilabel:`Signature Algorithm`
	      - ``RSA-SHA256``

	    * - :guilabel:`Digest Algorithm`
	      - ``SHA256``

	    * - :guilabel:`Assertion Encryption`
	      - ``Unencrypted``

      .. step:: Leave the remaining :guilabel:`Advanced Settings` fields in their
	 default state.

      .. step:: Scroll down to the :guilabel:`Attribute Statements (optional)`
	 section and create four attributes with the following values:

	 .. list-table::
	    :widths: 20 40 40
	    :header-rows: 1

	    * - Name
	      - Name Format
	      - Value

	    * - firstName
	      - Unspecified
	      - ``user.firstName``

	    * - lastName
	      - Unspecified
	      - ``user.lastName``

	 .. important::

	    The values in the **Name** column are case-sensitive. Enter
	    them exactly as shown.

	 .. note::

	    These values may be different if Okta is connected to an Active
	    Directory. For the appropriate values, use the Active Directory
	    fields that contain a user's first name, last name, and full
	    email address.

      .. step:: (Optional) If you plan to use 
	 :doc:`role mapping </security/manage-role-mapping/>`, 
	 scroll down to the 
	 :guilabel:`Group Attribute Statements (optional)` section 
	 and create an attribute with the following values:

	 .. list-table::
	    :widths: 25 25 25 25
	    :header-rows: 1

	    * - Name
	      - Name Format
	      - Filter
	      - Value

	    * - memberOf
	      - Unspecified
	      - Matches regex
	      - ``.*``

	 This filter matches all group names associated with the user. 
	 To filter the group names sent to Atlas further, 
	 adjust the :guilabel:`Filter` and :guilabel:`Value` fields.

      .. step:: Click :guilabel:`Next` at the bottom of the 
	 page.

      .. step:: On the :guilabel:`Feedback` screen, 
	 click :guilabel:`Finish`.
