# Change-Log for Apache Error Pages

Below is a detailed change-log, along with specific tasks completed, for each version released to date for Apache Error Pages.

## Version 1.1.0 (14/05/2018)

- [#new](#new)
  - New templates have been created as follows:
    - 520.html
    - 521.html
    - 533.html
  - Added `v1.0.0` of the `package.json` file which contains the dependencies for executing the `minify` script. You can run `$ npm install` from the project root folder and you _should_ have all the Node modules to run `$ ./scripts/minify`.
  - Added `postcss.config.js` to load the `cssnano` plugin.
- [#enhancement](#enhancement)
  - Optimised the `minify` script to now compress the JavaScript contained in the file along with any CSS inputs.
  - Optimised the CSS minification by using `postcss.config.js` to load the `cssnano` plugin which now reduces all CSS to one line of code.
  - New, minified versions for the CSS and HTML files have been created. The HTML templates are now one line of code as is the same with the CSS templates. File size has been reduced as follows:
    - CSS files: from `61 KB` to `44 KB` (`27.87%` file size reduction).
    - HTML files: from `46.3 KB` to `24.1 KB` (`47.95%` file size reduction).
  - Updated `README.md` to include all available HTTP error codes when modifying `httpd.conf`.
- [#bugfix](#bugfix)
  - Removed the commit of `html-minifier` to the project. This would prevent users from cloning the repo in order to run the minification script.

## Version 1.0.1 (14/05/2018)

- [#new](#new)
  - Added `CHANGELOG.md`, `CODE_OF_CONDUCT.md` and `CONTRIBUTING.md` files.
- [#enhancement](#enhancement)
  - Checked in Visual Studio Code workspace file for users of VS Code.
  - Install instructions now included in `README.md` file.
  - Updated `README.md` file with minifying setup included.
- [#bugfix](#bugfix)
  - Set absolute path to css folder (`/ErrorPages/css/`) to ensure that the resources load when running on a production server.
  - Rebuilt all `/dist/` files with the new changes.

## Version 1.0.0 (13/05/2018)

Grab everything you need from the `/dist/` folder. All other files support the creation of the files in this folder.

- [#new](#new)
  - HTML was minified but JavaScript is still unminified.
  - CSS has been minified although I am unclear what the advantage has been. (?)
- [#enhancement](#enhancement)
  - If you're insterested, there is a script that does the minification from source. This file is contained in [src/scripts/minify][script]. Simply run that file and it will:
    - Delete the `/dist/css/` folder.
    - Delete all the error pages (`rm -f ../dist/*.html`).
    - Recreate the `/dist/css/` folder.
    - Minify the HTML for all files in the `/src/` directory.
    - Minify the CSS for all the files in `/src/css/` directory.
    - Output the HTML and CSS to the `/dist/` folder.

[script]: src/scripts/minify