# Kick it!

Create Kickstarter apps with a snap.

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
gems by symlinking on of them or both from `~/.config/kick-it`
and calling CLI with a corresponding option: `kick-it -l`.

Example setup:
```
/Users/bob/.config/kick-it/infopark_cloud_connector -> /Users/bob/code/rails_connector/cloud_connector
/Users/bob/.config/kick-it/infopark_kickstarter     -> /Users/bob/code/kickstarter
```

## Usage

`kick-it APP_NAME`

This will create a Rails app, add appropriate gems and bundle it, generate features, reset and migrate the project.
When the script is done, chdir to the temp app and start the server.

`kick-it APP_NAME -l`

This will do basically the same, but will try to use local gem repositories if any provided.

## Version

`0.0.3`
