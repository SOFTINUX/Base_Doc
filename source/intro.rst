SOFTINUX Base Documentation
***************************

.. warning::
   The documentation is not complete and therefore undergoes frequent changes.

*SOFTINUX Base* is a free, open source and cross-platform based on |aspnetcore_link| and |extcore_link| framework.
It runs on Windows, Mac and Linux.
It is built using the best and the most modern tools and languages.

It is completely modular and extendable.

Using the features of the underlying ExtCore framework you can easily create your own extensions to extend its functionality.

Basic Concepts
==============
Softinux Base is a framework that looks like a .NET Core web application, but is intended to host mini web applications called extensions. Every extension will plug its content (pages, menu items) as well as security and authentication related items (permissions, roles, links...).

Base manages the common stuff so that the developer can focus on its extension and business logic, just having to provide what we call metadata to know how to display and authorize access to content, and use our version of Authorize attribute.

.. |aspnetcore_link| raw:: html

   <a href="https://docs.microsoft.com/en-us/aspnet/core/" target="_blank">ASP.NET Core</a>

.. |extcore_link| raw:: html

   <a href="http://extcore.net/" target="_blank">ExtCore</a>
