# wprig-testing

# Directions
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