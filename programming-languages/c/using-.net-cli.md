# Using .NET CLI

{% hint style="info" %}
Visit [Official documentation](https://docs.microsoft.com/en-us/dotnet/core/tools/) about .NET Core command-line interface \(CLI\) tools and commands.
{% endhint %}

To interact with .NET CLI tool we can type these commands in a command prompt or a shell or a terminal, depending of operating system in use, or in terminal inside VS Code.

Let's start .NET program we got when we installed .NET SDK:

Open cmd and type following commands:

1. **dotnet**

   ```text
   C:\Users\Milosh>dotnet

   Usage: dotnet [options]
   Usage: dotnet [path-to-application]

   Options:
     -h|--help         Display help.
     --info            Display .NET Core information.
     --list-sdks       Display the installed SDKs.
     --list-runtimes   Display the installed runtimes.

   path-to-application:
     The path to an application .dll file to execute.
   ```

2. **dotnet --info**

   \(provides with useful information if we need to troubleshoot our environment\)

   ```text
   C:\Users\Milosh>dotnet --info
   .NET Core SDK (reflecting any global.json):
    Version:   3.1.101
    Commit:    b377529961

   Runtime Environment:
    OS Name:     Windows
    OS Version:  10.0.18363
    OS Platform: Windows
    RID:         win10-x64
    Base Path:   C:\Program Files\dotnet\sdk\3.1.101\

   Host (useful for support):
     Version: 3.1.1
     Commit:  a1388f194c

   .NET Core SDKs installed:
     2.1.802 [C:\Program Files\dotnet\sdk]
     3.0.100 [C:\Program Files\dotnet\sdk]
     3.1.101 [C:\Program Files\dotnet\sdk]

   .NET Core runtimes installed:
     Microsoft.AspNetCore.All 2.1.13 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
     Microsoft.AspNetCore.All 2.1.15 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
     Microsoft.AspNetCore.App 2.1.13 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
     Microsoft.AspNetCore.App 2.1.15 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
     Microsoft.AspNetCore.App 3.0.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
     Microsoft.AspNetCore.App 3.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
     Microsoft.NETCore.App 2.1.13 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
     Microsoft.NETCore.App 2.1.15 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
     Microsoft.NETCore.App 3.0.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
     Microsoft.NETCore.App 3.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
     Microsoft.WindowsDesktop.App 3.0.0 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
     Microsoft.WindowsDesktop.App 3.1.1 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]

   To install additional .NET Core runtimes or SDKs:
     https://aka.ms/dotnet-download
   ```

3. **dotnet --help**

   \(provides with different SDK commands that are available with .NET\)

   ```text
   C:\Users\Milosh>dotnet --help
   .NET Core SDK (3.1.101)
   Usage: dotnet [runtime-options] [path-to-application] [arguments]

   Execute a .NET Core application.

   runtime-options:
     --additionalprobingpath <path>   Path containing probing policy and assemblies to probe for.
     --additional-deps <path>         Path to additional deps.json file.
     --fx-version <version>           Version of the installed Shared Framework to use to run the application.
     --roll-forward <setting>         Roll forward to framework version  (LatestPatch, Minor, LatestMinor, Major, LatestMajor, Disable).

   path-to-application:
     The path to an application .dll file to execute.

   Usage: dotnet [sdk-options] [command] [command-options] [arguments]

   Execute a .NET Core SDK command.

   sdk-options:
     -d|--diagnostics  Enable diagnostic output.
     -h|--help         Show command line help.
     --info            Display .NET Core information.
     --list-runtimes   Display the installed runtimes.
     --list-sdks       Display the installed SDKs.
     --version         Display .NET Core SDK version in use.

   SDK commands:
     add               Add a package or reference to a .NET project.
     build             Build a .NET project.
     build-server      Interact with servers started by a build.
     clean             Clean build outputs of a .NET project.
     help              Show command line help.
     list              List project references of a .NET project.
     msbuild           Run Microsoft Build Engine (MSBuild) commands.
     new               Create a new .NET project or file.
     nuget             Provides additional NuGet commands.
     pack              Create a NuGet package.
     publish           Publish a .NET project for deployment.
     remove            Remove a package or reference from a .NET project.
     restore           Restore dependencies specified in a .NET project.
     run               Build and run a .NET project output.
     sln               Modify Visual Studio solution files.
     store             Store the specified assemblies in the runtime package store.
     test              Run unit tests using the test runner specified in a .NET project.
     tool              Install or manage tools that extend the .NET experience.
     vstest            Run Microsoft Test Engine (VSTest) commands.

   Additional commands from bundled tools:
     dev-certs         Create and manage development certificates.
     fsi               Start F# Interactive / execute F# scripts.
     sql-cache         SQL Server cache command-line tools.
     user-secrets      Manage development user secrets.
     watch             Start a file watcher that runs a command when files change.

   Run 'dotnet [command] --help' for more information on a command.
   ```

