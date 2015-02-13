# gulp-dir-sync

Synchronizing directories plugin for Gulp.  Directories are watched and will sync continually while this plugin is running.

## USAGE

### Install

```
$ npm install gulp-dir-sync --save-dev
```

### Parameters

dirSync accepts 3 parameters:
source - the directory you want to clone
destination - the directory you want to clone to
options - an object that is used to pass the filter option - processing will only occur on files that match the filter

### Basic Example

#### dirSync(srcDir, destDir)

```javascript
var gulp = require('gulp');
var dirSync = require('gulp-dir-sync');

// Basic usage
gulp.task('sync', function() {
  dirSync('src/static', 'dist');
});
```

### Example with Filters

#### dirSync(srcDir, destDir, opts)

```javascript
var gulp = require('gulp');
var dirSync = require('gulp-dir-sync');

// Filtered usage
gulp.task('sync', function() {

  var dest = '/destination',
    source = '/source',
    opts = {};

  opts.filter = '^((?!\/\.git).)*$'; //add regex filter to match all paths that DO NOT have /.git in them (only process file if it does NOT NOT have /.git in it - double negative)
  dirSync(source, dest, opts);    
});
```

## License
Copyright (c) 2014 Yusuke Narita
Licensed under the MIT license.
