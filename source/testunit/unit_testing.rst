Unit testing
************

.. danger::

   **Obsolete**, to be rewritten, work in progress on rewriting unit test classes

xUnit and using database
========================
| Tests use xUnit, and for simplicity, a copy of example database.
| To run tests, you have to create the initial database in web application, seed it (for example using the REST API to create roles, users, permissions, then go to Chinook administration page and click on the button to fill Chinook data).
| Then copy basedb.sqlite from :guilabel:`/WebApplication` to :guilabel:`/Tests/Artefacts`.

Each time you run one or several tests, the database is copied from ``/Tests/Artefacts/basedb.sqlite`` to ``/Tests/WorkDir/basedb_tests.sqlite`` and this database is used.

ExtCore context
===========================================



We use the standard xUnit way to create a tests shared context (see ``BaseTest.Common.DatabaseFixture``) but we have to configure the Entity Framework db context, which database provider to use... Using ExtCore requires some configuration to be able to perform unit testings since there is no application services container and I wanted things to remain simple.

| So we provide a ``BaseTest.Common`` project that you can use.
| You have to define specific implementations:

- the ExtCore StorageContext implementation you wish to use. See an example in ``BaseTest.TestStorageContextBase`` that uses SQLite
- your TestContext implementation that references your storage context implementation. See an example in ``BaseTest.TestContext``.
- your ``DatabaseFixture`` implementation that references your TestContext implementations. See an example in ``BaseTest.DatabaseContext``.
- your ``DatabaseCollection`` class. See an example in BaseTest.DatabaseCollection and xUnit documentation. Cherry on the cake, done!

Don't forget that the relevant dlls should be added as reference to the unit test project, else you'll miss for example an ``IRepository`` implementation.