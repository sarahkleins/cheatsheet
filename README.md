# cheatsheet

# Git

# npm
* `npm init` to instantiate `package.json` file.
* `npm install <package> --save-dev` to add package to `devDependencies`
* `--save-dev` to save the package for development purposes. Example: unit tests, minification.
* `--save` to save the package required for the application to run.

# browserify
* Browserify makes it possible to `require` packages in the browser.
* `browserify <file-with-requires>.js -o bundle.js` || `browserify <file-with-requires>.js > bundle.js`.
* `-o` is `--outfile.` Write the browserify bundle to this file.
* `<script src='bundle.js'></script>` is in index.html file. 
* `scripts` object in package.json
* `scripts.test`
* `scripts.start`
* `scripts.build`

# jQuery
