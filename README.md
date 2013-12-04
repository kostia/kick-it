# Kick it!

Create Kickstarter apps with a snap.

## Installation

`brew install kick-it`. See https://github.com/kostia/homebrew-infopark.

## Configuration

Create a project in the Infopark-Console at https://console.infopark.net/ with CMS and CRM.
Download the configuration ZIP and unpack the files to `~/.config/kick-it`.


__WARNING__: This project will be resetted every time a new app is created, so please create a
project with a name expressing that fact.


## Usage

`kick-it APP_NAME`

This will create a Rails app, add appropriate gems and bundle it, generate features, reset and migrate the project.
When the script is done, chdir to the temp app and start the server.
