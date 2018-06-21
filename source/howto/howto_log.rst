How to log
==========
We've integrated Serilog by associating it to the logger factory that ASP.NET Core creates at application startup.

Log level is defined in ``appsettings.json`` of web application, sections "Logging" and "Serilog".

| To log a custom message, inject ``ILoggerFactory`` (:guilabel:`Microsoft.Extensions.Logging`) into your class constructor.
| Then instantiate your logger:

.. code-block:: c#

   Microsoft.Extensions.Logging.ILogger myLogger = _loggerFactory.CreateLogger(GetType().FullName);

and log: ``myLogger.LogInformation("Hello");``