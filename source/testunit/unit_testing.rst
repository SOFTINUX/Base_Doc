Unit testing
************

Introduction
============

| We use xUnit and its `shared context <https://xunit.github.io/docs/shared-context>`_ feature. Our base project is in `Testing/Unit/CommonTest`.
| It contains the ``DatabaseFixture`` class, that does several things:

 * read configuration files, register services (same principle as web application's Startup)
 * expose ExtCore core components such as ``IStorage`` to test classes
 * expose Identity ``RoleManager`` and ``UserManager`` to test classes

In addition, to perform an EF migration, an implementation of ``IDesignTimeDbContextFactory`` has been provided,
as CommonTest isn't a console but library project.

The test projects use an identical database to the one web application uses, but empty.

How to setup a test project
===========================
When you want to create a migration, be sure that your test project adds references to these projects:

* your extension's entities project (``YourExtension.Data.Entities``)
* your extension's EF project where lives *entities registrar* and repositories implementations (``YourExtension.Data.EntityFramework``)

If you just want to use ExtCore's *repositories* pattern to query DB, reference your extension's repositories project
``YourExtension.Data.EntityFramework``.