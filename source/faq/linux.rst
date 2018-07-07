Faq for Linux
*************

| **Q.** I have this message during the build: 
| ``Permission denied for editing the folder '/usr/share/dotnet/sdk/NuGetFallbackFolder'.``
| A.: You need to execute ``dotnet restore`` with root privilege because, the current user ave not right to write into ``/usr/share/dotnet/sdk/NuGetFallbackFolder``
