---
Title: Announcing Cake.AndroidAppManifest
Published: 2016/07/10
Tags:
  - xamarin android
  - androidmanifest
  - cakebuild
---
A [Cake Build](https://www.dotnetfoundation.org/blog/cake-welcome) addin for [de]serializing and updating an Android AppManifest is now available via [NuGet](https://www.nuget.org/packages/Cake.AndroidAppManifest/) or [GitHub](https://github.com/ghuntley/Cake.AndroidAppManifest/).

## Installation

Add the following reference to your cake build script:

```
#addin "Cake.AndroidAppManifest"
```

## Usage

```csharp
// load
var manifest = DeserializeAppManifest(new FilePath("AndroidManifest.xml"));

// adjust as needed
manifest.MinSdkVersion = 24;
manifest.PackageName = "com.example.mycoolapp";
manifest.VersionName = "1.0";
manifest.VersionCode = 10;
manifest.ApplicationIcon = "@mipmap/ic_launcher";
manifest.ApplicationLabel = "Android Application";
manifest.Debuggable = false;

// save
SerializeAppManifest(new FilePath("AndroidManifest.xml"), manifest);
```
