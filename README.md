#Team City xunit Meta Runner
===========================

Easily run [xunit](https://github.com/xunit/xunit) tests using [Team City](http://www.jetbrains.com/teamcity/).

This Team City plugin adds an extra option when creating a Build Step in Team City 'xunit'. This is currently quite simple and only allows the selection of one DLL containing xunit tests to be run. Wildcards and multiple assemblies are not supported (as this is not supported by the xunit console runner).

The plugin will copy a version of the xunit runner to all build agents to allow tests to be run without any additional configuration.
The plugin is currently using the 2.0.0 version of the xunit console runner (to run against ) and has been tested on Team City 9.0.1, but should work with any prior version of Team City.

## Installation

1. Copy the xunit2Runner folder AND the zipped folder to `<TeamCity Data Directory>/plugins`

The `xUnit2 Build Runner` build step type should now be available.

##MSBuild
MSBuild is supported and a build script is supplied that will zip the contents of the xunit2Runner up for you. It has a single dependency of [MS Build Tasks] https://github.com/loresoft/msbuildtasks

```shell
msbuild zip.msbuild /p:MSBuildCommunityTasksDirectory=[YourMSBuildTasksDirectory]
```