Installation
************

Restore npm packages
====================

After cloning *Base* repository, go to Barebone folder and run ``npm ci --save-dev`` command so that dependencies packages are installed and settings updated.

.. note::

   You must have |nodejs_link| to restore web dependencies.

Restore nuGet packages
======================

Restoring the nuGet packages is now an implicit command executed at application build so you don't need to do it manually.

Update database with migration
==============================

| Go to WebApplication folder and run ``dotnet ef database update``.
| This will create the database.
| See *appsettings.json* ("ConnectionStrings:Default" section) for database path.
| The Entity Framework database context is defined in web application's *Startup.cs* (line with ``services_.AddDbContext<...``).
| We use Sqlite but you can change this easily.

Build the application
======================

Go to the root folder and run ``bp.bat`` under Windows or ``bp.sh`` under Linux/Macos. (use -h for help).

.. note::

   You must have |netsdk_link| to compile and build the application.

Configure the application
=========================

| The application have some values to configure in ``appsettings.json`` file.
| Theses values are stored into sections:
| - Extensions : this is the path to find Extensions. **Important :** see :ref:`extensions folder <extension_folder>`.
| If you wish to change this path, read :ref:`what changes to make <configure_extension_folder>`.
| - ConnectionStrings : the connection configuration to database. See |connectionstring_link| to help you configure.
| - Corporate : the name and logo for the application
| - RestSeed : identification used to create admin user.

See :doc:`configuration section </configuration>` for a full explanation.

Run the app
===========

.. warning::

   Remove the ``SeedDatabase.dll`` to avoid any attempt to create a new administrator. See :ref:`config_seed` configuration section.

| Go to WebApplication folder and type ``dotnet run``.
| (If you want, you can also execute from root solution folder with this command ``dotnet run --project WebApplication\WebApplication.csproj``).

After that, the application is available on http://localhost:5000/

Note about Visual Studio 2017
-----------------------------

| If you launched application from Visual Studio, this port will change, being randomly defined, and value is stored in *WebApplication/Properties/launchSettings.json*
| You can edit this value in Visual Studio: WebApplication's properties > Debug tab > Web Server Settings/App URL or directly in launchSettings file.
| After, the default port used by `dotnet run` is the port defined in *WebApplication/Properties/launchSettings.json*.

Note about Rider 2017.3
-----------------------

| Rider 2017.3 cannot execute the PostBuildEvent declared into WebApplication.csproj
| You need to execute ``./bp.sh copyexts`` and ``./bp.sh copydeps`` after building the solution or project.
| Have a look after :doc:`Rider useful configuration section </howto/configure_rider>`.

Add the administrator user
==========================

| With Postman (or the program of your choice) make a POST request to this url: http://localhost:5000/dev/seed/create-user
| By command line:

- curl: ``curl -i -X POST -H 'Content-Type: application/json' http://localhost:5000/dev/seed/create-user -d {}``
- powershell: ``Invoke-WebRequest -Uri http://localhost:5000/dev/seed/create-user -Method POST``

This will create the administrator user with general permissions.

.. note::

   Actually, we creating demo user. The first user is johndoe.

Login with demo user
====================

| user: johndoe\@softinux.com or johndoe
| password: 123_Password
| (password is case sensitive)


.. |connectionstring_link| raw:: html

   <a href="https://www.connectionstrings.com/" target="_blank">connections strings</a>

.. |netsdk_link| raw:: html

   <a href="https://www.microsoft.com/net/download/" target="_blank">.NET Core SDK</a>

.. |nodejs_link| raw:: html

   <a href="https://nodejs.org/en/download/package-manager/" target="_blank">Nodejs</a>
