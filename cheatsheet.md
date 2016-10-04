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

# Mapbox
* Brew install gdal - ofr2ogr `brew install gdal`
* Transform shapefile to geoJSON `ogr2ogr -f GeoJSON new_geojson_file.geojson shapefile.dbf`
* Worked transforming large coordinates to long/lat (180/90)
* `ogr2ogr -t_srs EPSG:4326 -f geoJSON -lco COORDINATE_PRECISION=7 new_geojson_file.geojson shapefile.shp`
* [ogr2ogr docs] (http://www.gdal.org/ogr2ogr.html)
