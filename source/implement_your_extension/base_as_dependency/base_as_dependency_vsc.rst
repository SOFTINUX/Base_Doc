With commande line and Visual Studio Code
*****************************************

Create a new project
--------------------

.. code-block:: powershell

   $ dotnet new classlib -o <your_new_project> -f netcoreapp2.2

Open your new .csproj file and **adapt it with highlighted lines** as in example:

.. literalinclude:: ../../_static/src/SampleApi.csproj.txt
    :language: xml
    :caption: SampleApi csproj file
    :linenos:
    :emphasize-lines: 21,28,29,30,31-33,36-38

.. note ::
    | Path in `<HintPath>` are given as examples.
    | Lines 36 to 38 set the value of the Visual Studio `$(SolutionDir)` macro because `dotnet` doesn't use it.

.. include:: configure_vscode.rst
