Installation: version 2
***********************

Create the host webapp
======================

Create your solution folder. Create a ``src`` folder. In this folder, create an empty .NET Core webapp:

.. code-block:: bash

   $ dotnet new web -o SoftinuxBaseSample.WebApplication -f netcoreapp2.2

Go up in the root folder (above ``src``) and create the solution file:

.. code-block:: bash

   $ dotnet new sln

Add the webapp to the solution:

.. code-block:: bash

   $ dotnet sln add src/SoftinuxBaseSample.WebApplication/SoftinuxBaseSample.WebApplication.csproj

Go to the SoftinuxBaseSample.WebApplication directory, create an "Extensions" folder with a ".gitkeep" empty file
and adjust your .gitignore:

``# App Extensions
src/SoftinuxBaseSample.WebApplication/Extensions/*
!src/SoftinuxBasSample.WebApplication/Extensions/.gitkeep``

Edit your webapp's Program.cs, it should look like:

.. code-block:: csharp
    public class Program
    {
        public static void Main(string[] args)
        {
            CreateWebHostBuilder(args).Build().Run();
        }

        public static IWebHostBuilder CreateWebHostBuilder(string[] args_) =>
            WebHost.CreateDefaultBuilder(args_)
                .UseStartup<Startup>()
                // Add the two lines below for SoftinuxBase
                .UseWebRoot(Path.Combine(Directory.GetCurrentDirectory(), "..", "wwwroot"))
                .CaptureStartupErrors(true);
    }

Add the nuget packages
======================

For now we're testing locally generated and stored nuget packages.
Check "include prerelease" in nuget package manager if using Visual Studio.

Install these packages and the rest will follow (normally... but not now):

SoftinuxBase.Barebone
SoftinuxBase.Security
SoftinuxBase.WebApplication (to be created for "UseSoftinuxBase"/"AddSoftinuxBase" like ExtCore)
...
ExtCore.Data.EntityFramework (should be a dependency)
ExtCore.Mvc
ExtCore.WebApplication



TODO which packages to install

Temporarily
===========

Add your ApplicationStorageContext class that defines all the EF Core DbSets of your whole application.


Add SoftinuxBase to your Startup.csproj
=======================================

TODO once refactoring has been done, this should be a few lines.

Add the extension project
=========================

Link to Implement Your Extension


