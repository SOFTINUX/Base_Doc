Configure a new project with Visual Studio 2017/2019
****************************************************

Create new solution with a new ASP.NET Core project targeted on framework .NET Core 2.2.

Creation in Visual Studio 2019
-------------------------------
.. figure:: ../../_static/images/vs2019_add_new_project.png
   :alt: visual studio 2019 add new project

.. figure:: ../../_static/images/vs2019_add_new_project2.png
   :alt: visual studio 2019 add new project

Creation in Visual Studio 2017
-------------------------------
.. figure:: ../../_static/images/vs2017_add_new_project.png
   :alt: visual studio 2019 add new project

.. figure:: ../../_static/images/vs2017_add_new_project2.png
   :alt: visual studio 2019 add new project

Verification
------------
Check if your new project is targeted on framework .NET Core 2.2.

.. figure:: ../../_static/images/SampleExtensionConfig1.png
   :alt: sample extension configuration application tab

   Project properties, Application tab.

Add references
--------------

Add references to Base and ExtCore (ExtCore is dependency of Base)

.. figure:: ../../_static/images/SampleExtensiondeps1.png
   :alt: dependencies of sample application

Configure pre-build scripts
---------------------------
Before build, you need to copy all Base dependencies to `$(SolutionDir)$(OutDir)` folder:

.. image:: ../../_static/images/SampleExtensionPreBuild.png
   :alt: pre build tab configuration

Configure post-build scripts
----------------------------
After build, you need to copy your extension into base extension folder:

.. image:: ../../_static/images/SampleExtensionPostBuild.png
   :alt: post build tab configuration

Configure debug tab
-------------------
Must important, configure debugging.
You extension as a partial app and it's not directly executed. Here how to configure your application to make possibility of debugging.

.. image:: ../../_static/images/SampleExtensionDebugTabApp.png
   :alt: debug tab configuration

Now, you can debbug you extension into Visual Studio.

