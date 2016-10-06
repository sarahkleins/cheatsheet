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
