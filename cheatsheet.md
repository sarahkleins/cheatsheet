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

# Javascript
* From mdn: A common mistake for new JavaScript programmers is to extract a method from an object, then to later call that function and expect it to use the original object as its this (e.g. by using that method in callback-based code). Without special care however, the original object is usually lost. Creating a bound function from the function, using the original object, neatly solves this problem:

* `button.addEventListener('click', obj.function.bind(obj))`;
* `buton.addEventListener('click', state.forward.bind(state))`;


# jQuery

# Mapbox
* Brew install gdal - ofr2ogr `brew install gdal`
* Transform shapefile to geoJSON `ogr2ogr -f GeoJSON new_geojson_file.geojson shapefile.dbf`
* Worked transforming large coordinates to long/lat (180/90)
* `ogr2ogr -t_srs EPSG:4326 -f geoJSON -lco COORDINATE_PRECISION=7 new_geojson_file.geojson shapefile.shp`
* [ogr2ogr docs] (http://www.gdal.org/ogr2ogr.html)
