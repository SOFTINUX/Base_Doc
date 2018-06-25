Configuration
*************

| The configuration is made into ``appsettings.json`` file.
| You have many sections, but, only these sections must be need configuration.
- Extensions
- ConnectionStrings
- Corporate
- RestSeed

You can adapt others sections, but we not support it.

Extensions
----------

| By default, extensions ares stored into ``WebApplication\Extensions`` folder.
| But you can change this if you need. If you make that, you must change the variables into the build script :
- *bp.bat* for windows
- *bp.sh* for *nix system.

You have four variables :

- :envvar:`netVersion`: folder name defined by .NET Core TargetFramework tag into cs proj file.
- :envvar:`ext_folder`: extensions folder path.
- :envvar:`dep_folder`: dependencies folder path.
- :envvar:`pub_folder`: publish folder path.

.. code-block:: bat

  :: set .NET output folder name (use .NET Core version defined into csproj files)
  set netVersion="netcoreapp2.1"
  :: Extensions folder
  set ext_folder=".\WebApplication\Extensions\"
  :: Dependencies folder
  set dep_folder=".\WebApplication\bin\Debug\%netVersion%\"
  :: Publish folder
  set pub_folder=".\WebApplication\bin\Debug\%netVersion%\publish"

ConnectionStrings
-----------------

| In this section, you can configure your database connection.
| The file come with commented examples of connections strings.

.. code-block:: json

  "ConnectionStrings": {
      // Please use '/' for directory separator
      "Default": "Data Source=basedb.sqlite"
      // SqlServer
      //"Default": "Data Source=localhost;Initial Catalog=Softinux;MultipleActiveResultSets=True;Persist Security Info=True;User ID=softinux;Password=?"
      // PostgreSql
      //"Default": "Host=localhost;Port=5432;Database=softinux;Pooling=true;User ID=softinux;Password=?;"
      // localdb
      //"Default": "Data Source=(localdb)\mssqllocaldb;Database=softinux;Trusted_Connection=True;MultipleActiveResultSets=true"
    }

Corporate
---------

Here you can set you Company name and logo.

.. code-block:: json

  "Corporate": {
    "Name": "SOFTINUX",
    "BrandLogo": "softinux_logo-bg-transparent.png"
  }

The logo is to be place into : ``wwwroot\img``

.. _config_seed:

RestSeed
--------

| Here is the **SECRET** configuration for create first user.
| The first user is the application administrator.

.. code-block:: json

  "RestSeed": {
    "UserName": "",
    "UserPassword": "",
    "Id": "",
    "Guid": ""
  }

| You need to set these values.
| Id and Guid is used into REST api call to create admin user.

.. warning::

   Is strongly recommended to remove the ``SeedDatabase.dll`` to avoid any attempts to create a new administrator.
   This can happen if you change the information in the configuration file and restart the application.