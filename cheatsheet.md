# cheatsheet

# Git
* Merge in changes - 
```
cd to branch
git fetch origin
git merge origin/main-143-reviews-form
```
* Delete local branch - 
```
git branch -D [name-of-branch]
```
* Checkout new branch - 
```
git co -b new-branch-name
```

* Add remote - 
```
git remote -v
git remote add [name-of-remote] git@github.com:[github-user]/[github-repo].git
ex. git remote add karina git@github.com:karinaiparra/capmain-next.git
```

* Remove a remote - 
```
git remote rm karina (--> remote name)
```

* Add branch from another remote -
```
git co [name-of-remote]/[branch-name]
ex. git co karina/review-form

*follow instructions in msg*
```

* Pull from remote - 
```
git pull [remote] [branch-name]
ex. git pull venka tes-35-paginated-review
```

* Merge conflicts - 
```
git fetch upstream
git merge upstream/master --> or whatever branch you need to pull from i.e. upstream/refactorings
git st
Everything in GREEN in merged fine
Everything in RED needs to be resolved

<<<<<< HEAD is my code

============

<<<<<<< upstream/master is from upstream

git add file-name-where-changes-happend
git st
git commit
git push
```

* Rebase - 
```
git fetch upstream
git merge upstream/master
git push (for fork)
```

* Commit changes - 
```
git st
git diff [name-of-file]
git add [name-of-file]
git commit -m"message"
git push
```

* Add upstream - 
```
git remote add upstream git@github.com:capterra/vendor-portal-next.git (ORIGINAL - where to fetch from)
git remote add origin git@github.com:sarahkleins/vendor-portal-next.git (FORK!)
```

* To note - 
```
git push --set-upstream origin master
git push -u origin master 
are the same thing
```

# npm
* `npm init` to instantiate `package.json` file.
* `npm install <package> --save-dev` to add package to `devDependencies`
* `--save-dev` to save the package for development purposes. Example: unit tests, minification.
* `--save` to save the package required for the application to run.
* `npm run build` to use browserify/uglify -- bundle.js

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
* From mdn: A common mistake for new JavaScript programmers is to extract a method from an object, then to later call that function and expect it to use the original object as its this (e.g. by using that method in callback-based code). Without special care however, the original object is usually lost. Creating a bound function from the function, using the original object, neatly solves this problem (otherwise it thinks 'this' is the element. 'this' should be the original object the method came from):
* `element.addEventListener('click', obj.function.bind(obj))` || `button.addEventListener('click', state.forward.bind(state))`;

* `elem.classList.toggle(className)`

* Instance
* `attrControl` is an instance of `AttributionControl`...

* Works for device width check - `document.documentElement.clientWidth < 768 ? 'top-left' : 'bottom-right'`

```javascript
window.addEventListener('keydown', function(e) {
  const audio = document.querySelectorAll(`audio[data-key="${e.keyCode}"`])
  if (!audio) return;
  key.classList.add('playing');
}
```

```javascript
function removeTransition(){
  // function goes here
}

const keys = document.querySelectorAll('.key');
keys.forEach(key => key.addEventListener('transitionend', removeTransition))
```
`.bind(this)` 
- Can bind arguments to a function without invoking it, ex. `getData('GET', url, compileConversations.bind(this, cb)`
- First argument can be `this` (object it is referring to, function is acting on), `cb` would be first argument 

`.addEventListener(eventType, function, useCapture )`
- `useCapture`	Optional. A Boolean value that specifies whether the event should be executed in the capturing or in the bubbling phase. 

Possible values:
- `true` - The event handler is executed in the capturing phase
- `false` - Default. The event handler is executed in the bubbling phase

- `Event bubbling` - DOM elements can be nested inside each other. And somehow, the handler of the parent works even if you click on it’s child. The reason is event bubbling.

- `Capturing phase` Events first are captured down to deepest target, then bubble up. In IE9 they only bubble. 1-2-3.
- `Bubbling phase` Events first are captured down to deepest target, then bubble up. In IE9 they only bubble. 3-2-1.

### Adding Event Listeners
```javascript
function addEventListeners(list, event, func) {
  for (var i = 0, len = list.length; i < len; i++) {
     list[i].addEventListener(event, func, false);
  }
}
```
```javascript
addEventListenerCategories(category_filters, 'click', filterByCategory);
```
### event.target
`event.target` - A reference to the object that dispatched the event
`this` - Always refers to the DOM element the listener was attached to
`event.target` - Is the actual DOM element that was clicked
Log `this`, `event`, and `event.target` to see the differences


# ES6
`const` - constant
`${evaluate}` - ES6 template strings

# jQuery
* toggleClass
```javascript
_this.toggleClass('ba-flag-true', _this.text() == 'On'); //toggle class, if this is true
_this.toggleClass('ba-flag-true', _this.text() == 'Off'); //toggle class, if this is true
```

```javascript
$('.df-toggle-trigger').click(function(){
  var $icon = $(this).find('i'),
      $list = $(this).parents('.dropdown-toggle-container').find('.check-list'),
      hasUpArrow = $icon.hasClass('ss-navigateup');

  $icon.toggleClass('ss-navigatedown', hasUpArrow).toggleClass('ss-navigateup');
  $list.slideToggle(400);
});

/*
On click, If the parameter's value is false (the icon does not have ss-navigateup). 
'ss-navigatedown' is removed. 'ss-navigateup' is then added/removed appropriately. 
This all depends on the starting state, which is why it can seem confusing. 
On click, If the parameter's value is false (the icon does not have ss-navigateup), 
'ss-navigatedown' is removed. 'ss-navigateup' is then toggled (added).
*/
```

# CSS
* Media queries - see work_projects
```CSS
@media (min-width: 700px) { ... }
```
```CSS
@mixin clearfix {
  &::before,
  &::after {
    content: "";
    display: table;
    clear: both;
  }
}
```

* Positioning - 
```CSS
position: relative; /* element is positioned (top, right, bottom, left) relative to 
it's normal position (as a static element). */
```
```CSS
position: absolute; /* element is positioned (top, right, bottom, left) relative to 
it's first positioned (not `static`; `position: relative`) parent. */
```

# Ruby
* Update ruby verision - 
```
rbenv: version `2.3.1' is not installed
rbenv install 2.3.1
ruby -v
ruby 2.3.1
gem install bundler
bundle install
```

# Terminal
* Access local server - `ifconfig`
* Go to the beginning - `ctr a`
* Go the end - `ctr e`
* Delete backward - `ctr u`
* Delete forward - `ctr k`

# Mapbox
* Brew install gdal - ofr2ogr `brew install gdal`
* Transform shapefile to geoJSON `ogr2ogr -f GeoJSON new_geojson_file.geojson shapefile.dbf`
* Worked transforming large coordinates to long/lat (180/90)
* `ogr2ogr -t_srs EPSG:4326 -f geoJSON -lco COORDINATE_PRECISION=7 new_geojson_file.geojson shapefile.shp`
* [ogr2ogr docs] (http://www.gdal.org/ogr2ogr.html)
*  CSV to Map Points: `csv2geojson --lat latitude --lon longitude yext_points.csv | tippecanoe -o yext_v5.mbtiles -B3` ...large CSV tile to vector tile set (upload to Studio)
* http://gis.stackexchange.com/questions/127518/convert-csv-to-kml-or-geojson-etc-using-ogr2ogr-or-equivalent-command-line-tool - WORKS - large dataset from csv to geojson
* `tippecanoe -o [mbtiles_file].mbtiles -r1.5 -B12 [geojson_file].geojson`
* See how-to for csv-to-geojson-to-tileset


```javascript
map.addSource('metro-lines', {
  type: 'geojson', 
  data: '../data/features_connector_test.geojson'
});
```

```javascript
map.addSource('metro-stations', {
  type: 'vector', 
  url: 'mapbox://sarahkleins.civjtz97t02yc2tpbvjf98wy7-72tgh'
});
```

# Mapbox libraries
* [Turf.js](http://turfjs.org/) - geospatial (location data) analysis
* [Three.js](https://threejs.org/) - 3D library, WebGL
* [Chroma.js](http://gka.github.io/chroma.js/) - Color manipulation
* [d3.js](https://d3js.org/) - Manipulating documents based on data
* [arc.js](https://github.com/springmeyer/arc.js/blob/gh-pages/README.md) - Create arcs from lines
* [rbush.js](https://github.com/mourner/rbush) - 2D spatial indexing
* [Tippecanoe.js](https://github.com/mapbox/tippecanoe) - Builds vector tilesets from large collections of GeoJSON

# Update node
New versions of Node and NPM come out frequently. You can use Homebrew to update the software it installs.

Make sure Homebrew has the latest version of the Node package. In Terminal type `brew update`
Upgrade Node: `brew upgrade node`

# ESLint
* `npm test` to run
* `npm run fix` to run fixes
