# Hoovflight Configurator

Hoovflight Configurator is a crossplatform configuration tool for the Hoovflight flight control system.

It runs as an app within Google Chrome and allows you to configure the Hoovflight software running on any [supported Hoovflight target](https://github.com/hoovflight/hoovflight/tree/master/src/main/target).

There is also now a standalone version available, since Google Chrome Apps are getting deprecated on platforms that aren't Chrome OS. [Downloads are available in Releases.](https://github.com/hoovflight/hoovflight-configurator/releases)

Various types of aircraft are supported by the tool and by Hoovflight, e.g. quadcopters, hexacopters, octocopters and fixed-wing aircraft.

## Authors

Hoovflight Configurator is a [fork](#credits) of the Betaflight Configurator with support for Hoovflight instead of Cleanflight.

This configurator is the only configurator with support for Hoovflight specific features. It will likely require that you run the latest firmware on the flight controller.
If you are experiencing any problems please make sure you are running the [latest firmware version](https://github.com/hoovflight/hoovflight/releases/).

## Installation

### Standalone

Download the installer from [Releases.](https://github.com/hoovflight/hoovflight-configurator/releases)

### Development

1. Install node.js
2. Change to project folder and run `npm install`.
3. Run `npm start`.

### App build and release

The tasks are defined in `gulpfile.js` and can be run either via `gulp <task-name>` (if the command is in PATH or via `../node_modules/gulp/bin/gulp.js <task-name>`:

1. Optional, install gulp `npm install --global gulp-cli`.
2. Run `gulp <taskname> [[platform] [platform] ...]`.

List of possible values of `<task-name>`:
* **dist** copies all the JS and CSS files in the `./dist` folder.
* **apps** builds the apps in the `./apps` folder [1].
* **debug** builds debug version of the apps in the `./debug` folder [1].
* **release** zips up the apps into individual archives in the `./release` folder [1]. 

[1] Running this task on macOS or Linux requires Wine, since it's needed to set the icon for the Windows app (build for specific platform to avoid errors).

#### Build or release app for one specific platform
To build or release only for one specific platform you can append the plaform after the `task-name`.
If no platform is provided, all the platforms will be done in sequence.

* **MacOS** use `gulp <task-name> --osx64`
* **Linux** use `gulp <task-name> --linux64`
* **Windows** use `gulp <task-name> --win32`

You can also use multiple platforms e.g. `gulp <taskname> --osx64 --linux64`.

## Languages

Hoovflight Configurator has been translated into several languages. The application will try to detect and use your system language if a translation into this language is available. You can help [translating the application into your language](https://crowdin.com/project/hoovflight-configurator).

If you prefer to have the application in English or any other language, you can select your desired language in the options menu of the application.

### WebGL

Make sure Settings -> System -> "User hardware acceleration when available" is checked to achieve the best performance

### Linux users

Dont forget to add your user into dialout group "sudo usermod -aG dialout YOUR_USERNAME" for serial access

### Linux / MacOSX users

If you have 3D model animation problems, enable "Override software rendering list" in Chrome flags chrome://flags/#ignore-gpu-blacklist

## Developers

We accept clean and reasonable patches, submit them!

## Credits

ctn - primary author and maintainer of Baseflight Configurator from which Cleanflight Configurator project was forked.

Hydra -  author and maintainer of Cleanflight Configurator from which this project was forked.

[![Crowdin](https://d322cqt584bo4o.cloudfront.net/hoovflight-configurator/localized.svg)](https://crowdin.com/project/hoovflight-configurator)
