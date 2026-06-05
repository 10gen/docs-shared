Overview
--------

In this guide, you can learn about the BSON data format, how MongoDB
uses it, and how to install the BSON library independently of the
{+driver-short+}. 

BSON Data Format
----------------

BSON, or Binary JSON, is the data format that MongoDB uses to organize and store data.
This data format includes all JSON data structure types and also supports other types,
including dates, different size integers, ``ObjectId`` values, and
binary data. For a complete list of supported types, see the
:manual:`BSON Types </reference/bson-types>` page in the {+mdb-server+} manual.

The binary format is not human-readable, but you can use the
Java BSON library to convert it to a JSON representation.
To learn more about the relationship between these
formats, see the :website:`JSON and BSON </json-and-bson>` article.

MongoDB and BSON
----------------

The {+driver-short+}, which uses the BSON library, allows you to work
with BSON data by using one of the object types that implements the
`BSON interface <{+api-root+}/bson/org/bson/conversions/Bson.html>`__,
including:

- `Document <{+api-root+}/bson/org/bson/Document.html>`__ (BSON library package)
- `BsonDocument <{+api-root+}/bson/org/bson/BsonDocument.html>`__ (BSON library package)
- `RawBsonDocument <{+api-root+}/bson/org/bson/RawBsonDocument.html>`__ (BSON library package)
- `JsonObject <{+api-root+}/bson/org/bson/json/JsonObject.html>`__ (BSON library package)
- `BasicDBObject <{+core-api+}/BasicDBObject.html>`__ (JVM package)

To learn more information about using these object types, see the
|document-guide|.

Install the BSON Library
------------------------

This section shows how to add the BSON library as a dependency to
your project. If you added the {+driver-short+} as a dependency to your
project, you can skip this step since the BSON library is already included
as a required dependency of the driver. For instructions on how to add the
{+driver-short+} as a dependency to your project, see the
|get-started-guide|.

.. tip:: Bill of Materials

   We recommend adding the JVM driver Bill of Materials (BOM) to your
   application to manage the versions of driver artifacts. This removes
   the need to specify a version for any individual package covered by
   the BOM, simplifying dependency management. To learn more, see the |get-started-guide|.

We recommend that you use the `Maven <https://maven.apache.org/>`__ or
`Gradle <https://gradle.org/>`__ build automation tool to manage your project's
dependencies. Select from the following tabs to see the dependency declaration
for that tool:

.. tabs::

   .. tab:: Maven
      :tabid: maven-dependencies

      The following snippet shows the dependency declaration in the
      ``dependencies`` section of your ``pom.xml`` file.

      .. code-block:: xml

         <dependencies>
             <dependency>
                 <groupId>org.mongodb</groupId>
                 <artifactId>bson</artifactId>
             </dependency>
         </dependencies>

   .. tab:: Gradle
      :tabid: gradle-dependencies

      The following snippet shows the dependency declaration in the
      ``dependencies`` object in your ``build.gradle`` file.

      .. code-block:: groovy

         dependencies {
             compile 'org.mongodb:bson'
         }

If you are not using one of the preceding tools, you can include it in
your project by downloading the JAR file directly from the
`sonatype repository <https://repo1.maven.org/maven2/org/mongodb/bson/>`__.