# Wp Rig Sheridan Theme


## Getting Started

These instructions will get WP Rig Sheridan Theme up and running on your local machine for development and testing purposes. 

### Dependencies to install before the theme

1) [Php](http://php.net/) 7.0+ - server scripting language, and a powerful tool for making dynamic and interactive Web pages.

2) [NPM](https://www.npmjs.com/) - package manager
(installs latest version)

```
npm install npm@latest -g
```

3) [Yarn](https://yarnpkg.com/) - package/project manager
```
npm i yarn
```

4) [Node.js](https://nodejs.org/en/download/) -server-side JavaScript runtime environment. Download from Node website.

5) [Composer](https://getcomposer.org/) - Dependency Manager for PHP
(installed globally)

```
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

6) [Gulp](https://gulpjs.com/) - streaming build system in front-end web development

```
yarn install gulp-cli -g
yarn install gulp -D
```

*Built to integrate with [VS Code](https://code.visualstudio.com/) but can be used with any code editor


### Installing 

*** Using Yarn commands instead of NPM worked better. Many errors kept arrising with NPM. However you still need to have NPM installed. 

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

4. In command line, install necessary node and Composer dependencies.
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

### Additional info 
*[Wp Rig](https://github.com/wprig/wprig/) -  WP Rig theme one Github.
