# target-indicators.github.io
Docs for Target Indicators for Unity.

## DocFX commands
Instructions for updating API docs:

1. Make your change in the file and let Unity recompile. if its a comment only change, in rider build your solution from the unity project, not the assembly proejct. The way to know if it works is if the Generate button for XML in the assembly project is disabled.
2. Go to project root and find your assembly .csproj (e.g. TargetIndicators.csproj) and open it in rider
3. go to project file (TargetIndicators) and right click and select properties
4. under **Configuration** select **Debug | AnyCPU**
5. scroll down and find under XML Documentation "Generate" and enable it
6. change the Documentation file for the generated xml location to the `Library/ScriptAssemblies/TargetIndicators.xml`
7. click OK and Go to **Build > Clean Solution** then **Build > Solution**
8. Verify file was updated at the the location `Library/ScriptAssemblies/TargetIndicators.xml`
9. open CMD prompt at `Documentation~` location where `docfx.json` is located and run `docfx metadata`, then run `docfx build`
10. once that completes without warnings or errors run `docfx serve _site`
11. go to `localhost:8080` to confirm changes

## Instructions for updating docs site
1. make sure latest `docfx metadata` and `docfx build` have been run
2. copy all of the contents of the `_site`  into the other repository. don't copy `_site` folder itself, only the files and directories in it.
3. commit and push and the site should auto update
