Implement your own extension
============================

.. warning::

   You cannot place your Extentions folder to another drive. See `#2981 <https://github.com/dotnet/core-setup/issues/2981#issuecomment-322572374>`_

You can use `Visual Studio 2017 <https://www.visualstudio.com/fr/downloads/>`_, `Visual Studio Code <https://code.visualstudio.com/>`_ or `JetBrains Rider <https://www.jetbrains.com/rider/>`_ to make your own extension.
If you decide to use Visual Studio, be aware that projects are not compatible with Visual Studio 2015.

Add a new project
-----------------
Using command-line (easy and cross-platform):

.. code-block:: bash

   $ dotnet new classlib -o <you_new_project>

Add project reference to the solution
-------------------------------------
Go to solution folder and type:

.. code-block:: bash

   $ dotnet add reference <path_to_your_new_project>

Write your code
---------------
| In your new project, create a class that implements ``Infrastructure.IExtensionMetadata``.
| You may also implement ``Infrastructure.IExtensionDatabaseMetadata``.

Your extension will depend on Infrastructure.

Have a look at :doc:`write your extensions </write_extensions>`, feel free to open issues for questions.