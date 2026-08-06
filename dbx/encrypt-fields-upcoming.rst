=================
In-Use Encryption
=================

.. contents:: On this page
   :local:
   :backlinks: none
   :depth: 2
   :class: singlecol

Overview
--------

You can use the {+driver-short+} to encrypt specific document fields by using a
set of features called **in-use encryption**. In-use encryption allows
your application to encrypt data *before* sending it to MongoDB
and query documents with encrypted fields.

|driver-specific-content|

In-use encryption prevents unauthorized users from viewing plaintext
data as it is sent to MongoDB or while it is in an encrypted database. To
enable in-use encryption in an application and authorize it to decrypt
data, you must create encryption keys that only your application can
access. Only applications that have access to your encryption
keys can access the decrypted, plaintext data. If an attacker gains
access to the database, they can only see the encrypted ciphertext data
because they lack access to the encryption keys.

You might use in-use encryption to encrypt fields in your MongoDB
documents that contain the following types of sensitive data:

- Credit card numbers
- Addresses
- Health information
- Financial information
- Any other sensitive or personally identifiable information (PII)

MongoDB offers the following features to enable in-use encryption:

- :ref:`Queryable Encryption <subsection-qe>`
- :ref:`Client-side Field Level Encryption <subsection-csfle>`

.. _subsection-qe:

Queryable Encryption
~~~~~~~~~~~~~~~~~~~~

Queryable Encryption (QE) is an in-use encryption feature that
supports querying uniquely encrypted field values, including
equality, range, prefix, suffix, and substring queries. Range
query support requires MongoDB Server 8.0 or later. Prefix, suffix,
and substring query support requires MongoDB Server 9.0 or later.

To learn more about Queryable Encryption, see :manual:`Queryable
Encryption </core/queryable-encryption/>` in the Server manual.

.. _subsection-csfle:

Client-side Field Level Encryption
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Client-side Field Level Encryption (CSFLE) supports searching encrypted
fields for equality. MongoDB Server version 4.2 introduced CSFLE.

Unlike QE, CSFLE requires you to select an encryption
algorithm for each field, and that choice determines whether you can
query the field. Deterministic encryption always produces the same
output value for the same input value. Because matching values look
the same after encryption, you can run equality queries on these
fields. Randomized encryption produces a different output value each
time it encrypts the same input value. Drivers can decrypt these fields,
but you cannot query them.

Deterministic encryption trades some confidentiality for query support.
When an encrypted field has low cardinality, an attacker can compare
how often each encrypted value appears and infer the original values.
This technique is called frequency analysis. To protect fields that
you do not query, use randomized encryption.

.. tip::

   To learn more about these concepts, see the following Wikipedia
   entries:

   - :wikipedia:`Cardinality <w/index.php?title=Cardinality_(data_modeling)&oldid=1182661589>`
   - :wikipedia:`Frequency Analysis <w/index.php?title=Frequency_analysis&oldid=1182536787>`

To learn more about CSFLE, see :manual:`CSFLE </core/csfle/>` in the
Server manual.
