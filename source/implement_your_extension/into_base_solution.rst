New Extension into Base solution
********************************

Add a new project
=================
Using command-line (easy and cross-platform):

.. code-block:: bash

   $ dotnet new classlib -o <your_new_project> -f netcoreapp2.2

Assuming Base's ``Infrastructure`` framework version is 2.2. Check its .csproj file.

If you don't specify framework version, it will default to ``netstandardxxx``, which is not what we expect.

Add project reference to the solution
=====================================
Go to solution folder and type:

.. code-block:: bash

   $ dotnet sln add <path_to_your_new_project_csproj>

Write your code
===============
| In your new project, add a reference to Base's ``Infrastructure`` and also ``Security.Common``.
| Then create a ``ExtensionMetadata``  class that implements ``Infrastructure.IExtensionMetadata``.

Have a look at :doc:`write your extensions </extension_structure>`, feel free to open issues for questions.
