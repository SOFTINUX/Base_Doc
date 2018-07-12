Faq for Linux
*************

| **Q.** I have this message during the build:
| ``Permission denied for editing the folder '/usr/share/dotnet/sdk/NuGetFallbackFolder'.``
| A.: You need to execute ``dotnet restore`` with root privilege because, the current user ave not right to write into ``/usr/share/dotnet/sdk/NuGetFallbackFolder``

| **Q.** Th extension .NET Core Text Explorer cannot find unit Test
| A.: The problem is due to ``Permission denied for editing the folder '/usr/share/dotnet/sdk/NuGetFallbackFolder'.``
| You must declare and set the ``DOTNET_SKIP_FIRST_TIME_EXPERIENCE`` environment variable to 1 (or true)