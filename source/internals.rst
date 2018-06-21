Internals
*********

Implementations of ``IConfigureServicesAction`` They register services implementations to web application container so that they become available for dependency injection (ExtCore feature).

:guilabel:`Security` project:

- priority 200: ConfigureAuthentication
- priority 201: AddAuthorizationPolicies

Implementations of ``IConfigureAction`` They record web application's request pipelines (ExtCore feature).

:guilabel:`Security` project:

- priority 100: ActivateAuthentication