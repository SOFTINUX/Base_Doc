Implement your extension
****************************
.. _extension_folder:
.. warning::

   You cannot place your Extensions folder to another drive. See `#2981 <https://github.com/dotnet/core-setup/issues/2981#issuecomment-322572374>`_

You can use `Visual Studio 2017 <https://www.visualstudio.com/fr/downloads/>`_, `Visual Studio Code <https://code.visualstudio.com/>`_ or `JetBrains Rider <https://www.jetbrains.com/rider/>`_ to make your own extension.
If you decide to use Visual Studio, be aware that projects are not compatible with Visual Studio 2015.

Add a new project
=================
Using command-line (easy and cross-platform):

.. code-block:: bash

   $ dotnet new classlib -o <your_new_project> -f netcoreapp2.1

Assuming Base's ``Infrastructure`` framework version is 2.1. Check its .csproj file.

If you don't specify framework version, it will default to ``netstandardxxx``, which is not what we expect.

Add project reference to the solution
=====================================
Go to solution folder and type:

.. code-block:: bash

   $ dotnet sln add reference <path_to_your_new_project_csproj>

Write your code
===============
| In your new project, add a reference to Base's ``Infrastructure`` and also ``Security.Common``.
| Then create a ``ExtensionMetadata``  class that implements ``Infrastructure.IExtensionMetadata``.

Have a look at :doc:`write your extensions </extension_structure>`, feel free to open issues for questions.
