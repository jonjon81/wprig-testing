# Wprig Sheridan Wordpress Theme


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Dependencies to install before the theme

NPM

```
npm install
```

Node

```
Node install
```

Another

```
npm install
```

### Installing 

1. place the wprig-sheridan theme in the /wp-content/themes/ folder of your local development environment

2. WP Rig configuration
Open /dev/config/themeConfig.js and set the theme name, author name, and BrowserSync definitions to match your theme and your local development environment.

3. Configure VS Code
In VS Code, open Preferences (Ctrl/Cmd+,), go to Workspace Settings, and set the following configurations:

```
{
	"phpcs.enable": true,
	"phpcs.composerJsonPath": "wp-content/themes/[yourThemeFolder]/composer.json",
	"phpcs.standard": "WordPress",
	"editor.renderWhitespace": "all"
}
```

* Using Yarn instead of NPM worked better. Many errors kept arrising with NPM. 
4. In command line, run yarn run rig-init to install necessary node and Composer dependencies.
```
yarn run rig-init
```

5. Place the following in your ./config/config.local.json file. This config will not be tracked in your repo and will only be executed in your local development environment. Update the proxyUrl to match yours. 

```
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
```

6. In command line, to process source files, build the development theme, and watch files for subsequent changes.

```
yarn run dev
```

7. In WordPress admin, activate the WP Rig development theme.

End with an example of getting some data out of the system or using it for a little demo

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

## Key references

* [Wordpress](http://www.dropwizard.io/1.0.2/docs/) - Should start with new install
* [Another](https://maven.apache.org/) - Dependency Management
* [Another 2](https://rometools.github.io/rome/) - Used to generate RSS Feeds






