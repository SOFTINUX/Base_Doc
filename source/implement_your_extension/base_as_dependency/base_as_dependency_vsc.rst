With commande line and visaul Studio Code
*****************************************

Create a new project
--------------------

.. code-block:: bash

   $ dotnet new classlib -o <your_new_project> -f netcoreapp2.2

Open new csproj file and **adapt with highlighted lines** this example:

.. code-block:: xml
  :linenos:
  :emphasize-lines: 20,27,28,29,30,31,32

    <Project Sdk="Microsoft.NET.Sdk.Web">

        <PropertyGroup>
            <TargetFramework>netcoreapp2.2</TargetFramework>
            <AspNetCoreHostingModel>InProcess</AspNetCoreHostingModel>
            <ApplicationIcon />
            <OutputType>Library</OutputType>
            <StartupObject />
        </PropertyGroup>

        <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
            <NoWarn>1701;1702;1591</NoWarn>
        </PropertyGroup>

        <ItemGroup>
            <EmbeddedResource Include="Styles\**;Scripts\**\*.min.js;Views\**" />
        </ItemGroup>

        <ItemGroup>
            <PackageReference Include="ExtCore.Infrastructure" Version="4.1.0" />
            <PackageReference Include="Microsoft.AspNetCore.App" />
            <PackageReference Include="Microsoft.AspNetCore.Razor.Design" Version="2.2.0" PrivateAssets="All" />
            <PackageReference Include="Swashbuckle.AspNetCore" Version="4.0.1" />
        </ItemGroup>

        <ItemGroup>
            <Reference Include="SoftinuxBase.Infrastructure, Version=0.0.1.0, Culture=neutral, PublicKeyToken=null">
            <HintPath>..\..\Base\SoftinuxBase.Infrastructure.dll</HintPath>
            </Reference>
            <Reference Include="SoftinuxBase.Security.Common, Version=0.0.1.0, Culture=neutral, PublicKeyToken=null">
            <HintPath>..\..\Base\SoftinuxBase.Security.Common.dll</HintPath>
            </Reference>
        </ItemGroup>

        <Target Name="PreBuild" BeforeTargets="PreBuildEvent">
            <Exec Command="xcopy $(SolutionDir)..\..\Base\*.* $(SolutionDir)$(OutDir) /E /Y" />
        </Target>

        <Target Name="PostBuild" AfterTargets="PostBuildEvent">
            <Exec Command="mkdir $(SolutionDir)$(OutDir)Extensions&#xD;&#xA;copy $(SolutionDir)$(OutDir)SampleApi.dll $(SolutionDir)$(OutDir)Extensions /Y&#xD;&#xA;copy $(SolutionDir)$(OutDir)SampleApi.xml $(SolutionDir)$(OutDir)Extensions /Y" />
        </Target>

    </Project>
.. note ::
    Path in `<HintPath>` are given as esamples.




