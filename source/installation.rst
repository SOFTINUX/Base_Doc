Installation
************

Restore npm packages
====================

After, go to Barebone folder and run ``npm ci --save-dev`` command so that dependencies packages are installed and settings updated.

.. note::

   You must have `Nodejs <https://nodejs.org/en/download/package-manager/>`_ to restore web dependencies.

Restore nuget packages
======================

Restore the nuGet packages is now an implicit command executed at application build.

Update database with migration
==============================

| Go to WebApplication folder and run ``dotnet ef database update``.
| This will create the database.
| See *appsettings.json* for database path.
| The Entity Framework database context is defined in web application's *Startup.cs*.
| We use Sqlite but you can change this easily.

Build the appplication
======================

Go to the root folder and run ``bp.bat`` under Windows or ``bp.sh`` under Linux/Macos. (use -h for help).

.. note::

   You must have `.NET Core SDK <https://www.microsoft.com/net/download/windows>`_ to compile and build the application.

Run the app
===========

| Go to WebApplication folder and type ``dotnet run``.
| (If you want, you can also execute from root solution folder with this command ``dotnet run --project WebApplication\WebApplication.csproj``)

After that, the application is available on http://localhost:5000/

Note about Visual Studio 2017
-----------------------------

| If you launched application from Visual Studio, this port will change, being randomly defined, and value is stored in *WebApplication/Properties/launchSettings.json*
| You can edit this value in Visual Studio: WebApplication's properties > Debug tab > Web Server Settings/App URL or directly in launchSettings file.
| After, the default port used by :guilabel:`dotnet run` is the port defined in *WebApplication/Properties/launchSettings.json*.

Note about Rider 2017.3
-----------------------

| Rider 2017.3 cannot execute the PostBuildEvent declared into WebApplication.csproj
| You need to execute ``./bp.sh copyexts`` and ``./bp.sh copydeps`` after build the solution or project.

Add the first user (demo user)
==============================

| With Postman (or the program of your choice) make a POST request to this url: http://localhost:5000/dev/seed/CreateUser
| (with curl: ``curl -i -X POST -H 'Content-Type: application/json' http://localhost:5000/dev/seed/CreateUser -d {}``)
| This will create the demo user with general permissions.

Login with demo user
====================

| user: johndoe@softinux.com
| password: 123_Password
| (password is case sensitive)