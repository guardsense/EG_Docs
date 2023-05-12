# README

This project contains the documentation website generated using docfx. To view the website in its correct form, it must be deployed as instructed in [DocFX Getting Started](https://dotnet.github.io/docfx/index.html).

For instructions on how to generate and deploy documentation for the code located in [EG_Source](https://github.com/guardsense/EG_Source), use the steps defined below.

## <u>Generating Documentation</u>

To generate documentation using docfx:

1. Install docfx as a global tool using the command:

   ​	`dotnet tool update -g docfx`

2. Comment out `using CLI;` in both `CpuInfo.cs` and `CpuTrackerService.cs`

3. Uncomment `using EnergyPerformance.Temporary;` in **both** these files.

4. Comment out `<ProjectReference Include="..\Wrapper\Wrapper.vcxproj" />` in `EnergyPerformance.csproj`.
   This will remove the reference to the Wrapper project which contains the C++/CLI code, as docfx does not support these
   files.

5. Run the following command in a new terminal inside the `docs` folder:

   ​	`docfx docfx.json --serve`

   This will build the documentation and deploy the website to http://localhost:8080/.

6. After viewing the website, press `Ctrl + C` or close the terminal, to stop hosting the website.

7. **Undo all the changes** specified in instructions 2-4. Feel free to use Git to discard these changes to speed up this process.

8. For more information about docfx and getting started, visit the official [website](https://dotnet.github.io/docfx/index.html).







