About Entity Framework
**********************

By definition, ExtCore uses Entity Framework but provides several projects to define:

- the entities in ``YourExtension.Data.Entities``
- the entities mapping in ``YourExtension.Data.EntityFramework`` (``EntityRegistrar`` class)
- the EF provider to actually use, in ``YourExtension.Data.EntityFramework.ProviderName``

| The ``SecurityTest`` test project in ``Testing/Unit`` references the three aforementioned projects related to ``Security`` extension
| and also uses ``CommonTest.ApplicationStorageContext`` class to indicate the DbContext structure.
