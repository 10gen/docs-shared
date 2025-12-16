ACID transactions guarantee atomicity, consistency, isolation, and
durability so that database operations are executed safely, even
when failures occur. ACID transactions are required in some industries where
errors or partial updates could lead to serious financial, legal, or safety
consequences.

By default, operations on single documents conform to ACID standards. For
operations on multiple documents or collections, MongoDB supports multi-document
ACID transactions using sessions. These transactions use snapshot isolation so
applications see a consistent set of data while the transaction is running, and
they use write concerns to make sure changes are safely saved.