# Heroku Buildpack: .NET Core

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for .NET Core apps.

It uses the `dotnet-install.sh` script to install the .NET SDK and Runtime.

## Usage

Create a new app with this buildpack:

```bash
$ heroku create --buildpack https://github.com/H-ADV/heroku-buildpack-dotnet10core.git
```

Or add it to an existing app:

```bash
$ heroku buildpacks:set https://github.com/H-ADV/heroku-buildpack-dotnet10core.git
```

## .NET Version

The buildpack will install the .NET SDK version specified in `global.json` or fallback to the latest supported version if not specified.

To specify a version, create a `global.json` file in the root of your repository:

```json
{
  "sdk": {
    "version": "10.0.100"
  }
}
```

Or specify `<TargetFramework>net10.0</TargetFramework>` in your `.csproj` file.
