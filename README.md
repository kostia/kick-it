# Kick it!

Create Kickstarter apps with a snap.

![Kick-it](https://raw.github.com/kostia/kick-it/master/kick-it.png)

## Installation

`brew install kick-it`. See https://github.com/kostia/homebrew-infopark.

## Configuration

### Project

Create a project in the Infopark-Console at https://console.infopark.net/ with CMS and CRM.
Download the configuration ZIP and unpack the files to `~/.config/kick-it`.

__WARNING__: This project will be resetted every time a new app is created, so please create a
project with a name expressing that fact.

### Local repositories

You can use local repositories of the `infopark_cloud_connector` or the `infopark_kickstarter`
gems by symlinking them from `~/.config/kick-it`.

```bash
# ~/.config/kick-it/infopark_cloud_connector -> ~/code/rails_connector/cloud_connector
# ~/.config/kick-it/infopark_kickstarter     -> ~/code/kickstarter
```

## Usage

`kick-it APP_NAME`

This will create a Rails app, add appropriate gems and bundle it, generate features, reset and migrate the project.
When the script is done, chdir to the temp app and start the server.

`kick-it APP_NAME -L`

This will do basically the same, but will try to use local gem repositories if any provided.

For more options see the help: `kick-it -h`.

## Version

`0.0.4`
