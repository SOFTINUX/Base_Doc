Visual Studio Code Configuration
--------------------------------

Tasks.json
^^^^^^^^^^
| Add lines 26 to 29 and 38 to 40.
| Modify line 35 to use :code:`WebApplication.dll` as entry point of application.

.. note::
   The order sequence make build on every launch.

.. literalinclude:: ../../_static/src/tasks.json
    :language: js
    :caption: SampleApi Visual Studio Code tasks file
    :linenos:
    :emphasize-lines: 26-29,35,38-40

Launch.json
^^^^^^^^^^^
| Modify line 13 to use :code:`WebApplication.dll` as the program to execute.
| Modify line 15 to specify execution folder.

.. literalinclude:: ../../_static/src/launch.json
    :language: js
    :caption: SampleApi Visual Studio Code launch file
    :linenos:
    :emphasize-lines: 13,15
