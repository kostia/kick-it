# Kick it!

Create Kickstarter apps with a snap.

![Kick-it](https://raw.github.com/kostia/kick-it/master/kick-it.png)

## Installation

`brew install kick-it`. See https://github.com/kostia/homebrew-infopark.

## Configuration

1. Create a project in the Infopark-Console at https://console.infopark.net/ with CMS and CRM.
For security reasons a project used with this tool __must__ include a special string `kickme`
in it's name, e.g. `fookickme123`.

2. Download and import the configuration ZIP:
```bash
kick-it -i ~/Downloads/fookickme123-config.zip
```

3. Change global configuration (if you wish):
```bash
kick-it -e
```

Global configuration file is placed in `~/.config/kick-it/config.yml`.
Default project configuration files are kept in `~/.config/kick-it/`.

## Usage

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

## Special cases

### Local repositories

When developing on Infopark gems, you may wish to generate an app, which uses you local repositories.
You can use local repositories of the `infopark_cloud_connector` or the `infopark_kickstarter`.

1. Add the corresponding keys `cloud_connector` and `kickstarter` with appropriate paths in the global configuration:
```bash
kick-it -e
```

2. You can now kick the apps using local gems:
```bash
kick-it my_app -l # Use all gems
kick-it my_app -c # Use only Infopark Cloud Connector gem
kick-it my_app -k # Use only Infopark Kickstarter gem
```

### Multiple projects

You can have several different projects configurations. For example: you want to have one app,
on which you develop for a long period of time and another app, on which you want to check something quickly.
Both apps can't share same project, because they would reset each others content.

1. Import a named alternative project configuration:
```bash
kick-it -i ~/Downloads/fookickme123-config.zip -p do_not_reset_me
```

2. Then you can generate an app with this configuration:
```bash
kick-it my_feature_app -p do_not_reset_me
```

Named alternative project configuration files are kept in `~/.config/kick-it/PROJECT_NAME`.

### Persisting generated apps

By default the apps will be generated in `/tmp/kicks` and thus would not survive a reboot.
In order to "persist" the generated apps you have to change the
corresponding key `kicks_home` in the global configuration.

## Version

`0.0.6`
