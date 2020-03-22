# Wprig Sheridan Wordpress Theme


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Prerequisites

What things you need to install the software and how to install them

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc











# Directions to setup locally
1. place the wprig-sheridan theme in the /wp-content/themes/ folder of your local development environment

2. WP Rig configuration
Open /dev/config/themeConfig.js and set the theme name, author name, and BrowserSync definitions to match your theme and your local development environment.

3. Configure VS Code
In VS Code, open Preferences (Ctrl/Cmd+,), go to Workspace Settings, and set the following configurations:

{
	"phpcs.enable": true,
	"phpcs.composerJsonPath": "wp-content/themes/[yourThemeFolder]/composer.json",
	"phpcs.standard": "WordPress",
	"editor.renderWhitespace": "all"
}

4. In command line, run yarn run rig-init to install necessary node and Composer dependencies.

5. Place the following in your ./config/config.local.json file. This config will not be tracked in your repo and will only be executed in your local development environment. Update the proxyUrl to match yours. 

{
    "dev": {
      "browserSync": {
        "live": true,
        "proxyURL": "localhost:8888/wordpress-two",
        "bypassPort": "8181",
        "https": false
      }
    }
}

6. In command line, run npm run dev to process source files, build the development theme, and watch files for subsequent changes.

7. In WordPress admin, activate the WP Rig development theme.