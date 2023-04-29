# Reloaded Project Configurations

This page hosts the common configurations for various parts of the Reloaded project.

This includes:  
- `.editorconfig` files for configuring code style.  
- `Tests.Build.props` for common project settings for tests.  
- `NuGet.Build.props` for common project settings that target NuGet.  
- `Directory.Build.props` for common project settings.  
- `Directory.Build.targets` for common project targets.  

## Usage

To use this repository, add it as a submodule to your project.

```
git submodule add https://github.com/Reloaded-Project/Reloaded.Project.Configurations.git ./Source/Reloaded.Project.Configurations
```

Periodically update the submodule to the latest version.

```
git submodule update --remote
```

### Tests.Build.props

For test projects, modify your `.csproj` to include `Tests.Build.props` as follows:

```xml
<Import Project="../Reloaded.Project.Configurations/Tests.Build.props" />
```

### NuGet.Build.props

For packages that are shipped to NuGet, modify your `.csproj` to include `NuGet.Build.props` as follows:

```xml
<Import Project="../Reloaded.Project.Configurations/NuGet.Build.props" />
```

The following remaining properties should be manually specified per package:
```xml
<PackageProjectUrl>https://github.com/Reloaded-Project/Reloaded.Memory</PackageProjectUrl>
<Description>Package Description.</Description>
<Version>1.0.0</Version>
<Product>Cool Library Name</Product>
```

### Directory.Build.props

For any other projects, modify your `.csproj` to include `Directory.Build.props` as follows:

```xml
<Import Project="../Reloaded.Project.Configurations/Directory.Build.props" />
```

## Code Style

The code style is defined in the `.editorconfig` file in the root of the repo.

To apply this to your project, do the following:

- Enable symlinks for your current project by running `git config core.symlinks true`.
- Make symlink to `Reloaded.Project.Configurations/.editorconfig` in the root of your project.
- On Windows this can be done by running `mklink .editorconfig Reloaded.Project.Configurations/.editorconfig`.
- Or on Linux, you can do `ln -s Reloaded.Project.Configurations/.editorconfig .editorconfig`.

### .solutionItems

In each project you should make a `.solutionItems` folder and add any useful files (as existing files) from the folder
the `.sln` is contained in; such that it's visible from the IDE.

## Documentation

If documentation is required, please follow the guidelines for [Reloaded MkDocs Theme](https://reloaded-project.github.io/Reloaded.MkDocsMaterial.Themes.R2/Pages/) 
on how to set up documentation.

## License

This repository is licensed under the LGPLv3 license; as per the license of the Reloaded Project (sans. Reloaded
II/Reloaded3).
