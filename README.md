
# Treehouse .NET Local Code Challenges Test Project

This .NET console app project is intended as a test project to assist with setting up and testing .NET local code challenges.

The root of the repo contains an MSBuild file (`project.msbuild`) that will build the project, run all of the tests, and if all of the tests successfully pass creates a ZIP file (project.zip) containing all of the source code files located in the `src` folder.

To run the MSBuild script, execute the following command in the root of the repo:

```
msbuild project.msbuild
```

In the `TreehouseDefenseTests/MapTests.cs` file, you can uncomment the following "always failing" test in order test that the MSBuild script will not create the project ZIP file if there's a failing test.

```
[Fact()]
public void AlwaysFail()
{
    Assert.True(false);
}
```

## Dependencies

The following packages need to be installed as dependencies in the test project in order to support xUnit and creating a ZIP file from the MSBuild script:

xunit
xunit.runner.console
xunit.runner.msbuild
MSBuildTasks

## Running Tests from the Command Line

Run the following commands from the root of the repo to build the solution and run all tests in the test project:

```
msbuild src/TreehouseDefense.sln
mono src/packages/xunit.runner.console.2.2.0/tools/xunit.console.exe src/TreehouseDefenseTests/bin/Debug/TreehouseDefenseTests.dll
```
