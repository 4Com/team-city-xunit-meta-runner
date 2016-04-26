#[Deprecated] Team City xunit Meta Runner
===========================

Deprecation: This runner was built when xunit meta-runners were not available for TeamCity. Since then, [more supported, official ones](https://github.com/JetBrains/meta-runner-power-pack/tree/master/xUnit.net-dotCover) have become available and will probably aid your team better.

Easily run [xunit](https://github.com/xunit/xunit) tests using [Team City](http://www.jetbrains.com/teamcity/).

This Team City plugin adds an extra option when creating a Build Step in Team City 'xunit2'. This is currently quite simple and only allows the selection of one DLL containing xunit tests to be run. Wildcards and multiple assemblies are not supported (as this is not supported by the xunit console runner).

The plugin will copy a version of the xunit runner to all build agents to allow tests to be run without any additional configuration and *can coexist with previous versions of this plugin*.
The plugin is currently using the 2.0.0 RTM version of the xunit console runner (to run against) and has been tested on Team City 9.0.1, but should work with versions 8.0.0 > 9.0.x.

## Installation

1. Download your selected package.
2. From within the administration panel in TeamCity, select "Plugins List" and then "Upload plugin zip". This may require a restart of the TeamCity service, depending on version*.
3. This can now be consumed just like a typical plugin.

*Since version 9.0.0 of Team City, changes to this folder are automatically detected and the plugin will be distributed to all of your build agents. Prior to version 9.0.0 you will need to restart the Team City service.

##MSBuild
MSBuild is supported and a build script is supplied that will zip the contents of the xunit2Runner up for you. It has a single dependency of [MS Build Tasks](https://github.com/loresoft/msbuildtasks)

```Powershell
msbuild zip.msbuild /p:MSBuildCommunityTasksDirectory=[YourMSBuildTasksDirectory]
```
