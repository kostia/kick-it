# Kick it!

Create [Infopark Kickstarter](https://dev.infopark.net/kickstarter) apps with a snap.

![Kick-it](https://raw.github.com/kostia/kick-it/master/kick-it.png)

## Installation

`brew install kick-it`.

See also https://github.com/kostia/homebrew-infopark.

## Configuration

1. Create a new project at https://console.infopark.net/ with a CMS and a CRM (see [Getting started](https://dev.infopark.net/getting-started) for details).
For security reasons this project __MUST__ include a special string `kickme` in it's name, e.g. `fookickme123`.

2. Download and import the configuration ZIP:
```bash
kick-it -i ~/Downloads/fookickme123-config.zip
```
See also [multiple project configurations](https://github.com/kostia/kick-it/wiki/Multiple-project-configurations).

## Usage

```bash
kick-it APP_NAME
```

Full list of options:
```
  Generate an app:           kick-it APP_NAME [-cklfq] [-p PROJECT_NAME]
  Open an app:               kick-it -o APP_NAME
  Edit global configuration: kick-it -e
  Import project ZIP:        kick-it -i PATH_TO_ZIP [-p PROJECT_NAME]
  Help and version:          kick-it [-hv]

    -c, --local-cloud-connector      Use local repo for Infopark Cloud Connector gem
    -k, --local-kickstarter          Use local repo for Infopark Kickstarter gem
    -l, --local                      Use local repos for all Infopark gems
    -f, --force                      Skip all confirmations (assume as confirmed)
    -q, --quiet                      Minimize the output
    -o, --open-app app_name          Open kicked app in $EDITOR
    -e, --edit-config                Open configuration file in $EDITOR
    -i, --import path                Import project settings ZIP
    -p, --project project_name       Use alternative project configuration
    -v, --version                    Print the version number
```

## Documentation

Take a look at the [Wiki](https://github.com/kostia/kick-it/wiki):

* [Using local repositories](https://github.com/kostia/kick-it/wiki/Using-local-repositories)
* [Multiple project configurations](https://github.com/kostia/kick-it/wiki/Multiple-project-configurations)
* [Persisting generated apps](https://github.com/kostia/kick-it/wiki/Persisting-generated-apps)

## Version

`0.0.7`
