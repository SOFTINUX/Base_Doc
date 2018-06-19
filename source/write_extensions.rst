Basics
======

Extensions common interface
---------------------------
In your extension project, a class should implement the ``Infrastructure.IExtensionMetadata`` interface,
so that the application knows what the extension provides in matter of display (menu items)...

Menu groups and menu items
--------------------------
Menu groups are ordered by position then alphabetically.
They're not displayed if they contain no menu items. The first occurrence of a menu group defines the associated icon. Menu items (of a menu group) are ordered by position.

Controllers
-----------
Your controllers should inherit from ``Infrastructure.ControllerBase`` so that you have access to storage layer (``IStorage``) and optionally logging (``ILoggerFactory``).

Logging
-------
When you need logging, use ``ILoggerFactory`` from your controller and instantiate a private logger in your class with ``ILogger _logger = _loggerFactory.CreateLogger(GetType().FullName);``

Then you can adjust log level in app's configuration.

Providing additional configuration to web application
=====================================================
Any implementation of the ``ExtCore.Infrastructure.Actions.IConfigureServicesAction`` interface allows you to define your injections to the web application services container.
Please use Priority above 1000, the values below are reserved to project.

Permissions, Scopes and Claims
==============================
Our application uses claims to grant access to protected pages.

An extension defines its scope (assembly simple name) so that the Admin, Write and Read permissions are granted by scope. There is also the global scope that is named "Security".

In administration interface you can manage how the permissions are granted.

In your extensions controllers, use ``PermissionRequirementAttribute`` or ``AnyPermissionRequirementAttribute`` attribute from ``Security.Common.Attributes``.
Then provide the permission level (see ``Security.Common.Enums.Permission enumeration``) and scope (extension assembly short name without the version and culture stuff).

A custom claim of type Permission will be created for every scope, its value being the highest permission level.
For example, if the "Write" and "Read" checkboxes are checked for a given scope in administration page, the highest granted permission level is "Write" and the claim will have "Write" value.

You will be able to use it to filter menu items too (work in progress, issue `#9 <https://github.com/SOFTINUX/Base/issues/9>`_).