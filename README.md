# Kick it!

_Create_ [_scrivito_](https://scrivito.com) _apps_ _with_ _a_ _snap_...

![Kick-it](https://raw.github.com/kostia/kick-it/master/kick-it.png)

With [Kick it](https://github.com/infopark/kick-it) you can easily generate new scrivito apps.
You can configure them to use gems from your local repos,
you can select which tenant should be used for which app and much more.

## Installation

```bash
brew tap kostia/infopark # Attention: the repository location may change.
brew install kick-it
```

See also https://github.com/kostia/homebrew-infopark.

## Configuration

1. Create a new project (see https://scrivito.com/getting-started for details).
For security reasons this project __MUST__ include a special string `kickme` in it's name, e.g. `fookickme123`.
2. Download and import the configuration ZIP: `kick-it -i ~/Downloads/fookickme123-config.zip`
3. Optionally edit global configuration: `kick-it -e`

## Usage

```bash
kick-it APP_NAME        # Kick new app
kick-it APP_NAME -lfq   # Kick new app using local gems, override everything without asking and be quite.
```

Full list of CLI options:
```
  Generate an app:           kick-it APP_NAME [-lfq] [-p PROJECT_NAME]
  Open an app:               kick-it -o [APP_NAME]
  Edit global configuration: kick-it -e
  Import project ZIP:        kick-it -i PATH_TO_ZIP [-p PROJECT_NAME]
  Help and version:          kick-it [-hv]

    -l, --local                      Use local repos for all Infopark gems (specify the gems in the config)
    -f, --force                      Skip all confirmations (assume as confirmed)
    -q, --quiet                      Minimize the output
    -o, --open-app [app_name]        Open kicked app in $EDITOR or the apps home
    -e, --edit-config                Open configuration file in $EDITOR
    -i, --import path                Import project settings ZIP
    -p, --project project_name       Use alternative project configuration
    -v, --version                    Print the version number
```

Full list of global configuration keys:
```yaml
# Find me in '~/.config/kick-it/config.yml'.
# Edit me with 'kick-it -e' command.

# Where to put the generated apps.
kicks_home: '~/.kick-it'

# Local respositories for Infopark gems.
scrivito:                 '/Users/bob/Code/rails_connector/scrivito'
scrivito_kickstarter:     '/Users/bob/Code/scrivito_kickstarter'
scrivito_editors:         '/Users/bob/Code/scrivito_editors'
scrivito_resourcebrowser: '/Users/bob/Code/scrivito_resourcebrowser'

# Default options for kicking apps.
force: false # Same as the "-f" CLI option.
local: false # Same as the "-l" CLI option.
quiet: false # Same as the "-q" CLI option.
```

## Documentation

Take a look at the [Wiki](https://github.com/infopark/kick-it/wiki):

* [Using local repositories](https://github.com/infopark/kick-it/wiki/Using-local-repositories)
* [Multiple project configurations](https://github.com/infopark/kick-it/wiki/Multiple-project-configurations)
* [Running server in production environment](https://github.com/infopark/kick-it/wiki/Running-server-in-production-environment)
* [Visual dialog](https://github.com/infopark/kick-it/wiki/Visual-dialog)

## License

[LGPG-3.0](http://www.gnu.org/licenses/lgpl-3.0.html) License.
Copyright 2013 Infopark AG.
http://www.infopark.com

## Version

`0.4.3`
