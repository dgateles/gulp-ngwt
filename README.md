# gulp-ngwt [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url]

A fork from tatsuyafw/gulp-nightwatch

## Usage

First, install `gulp-ngwt` as a development dependency:

```sh
npm install --save-dev gulp-ngwt
```

Then, write your gulpfile.js as below.

```javascript
var gulp = require('gulp'),
    nightwatch = require('gulp-ngwt');

gulp.task('default', function() {
  return gulp.src('gulpfile.js')
    .pipe(nightwatch({
      configFile: 'test/nightwatch.json'
    }));
});
```

You can pass command line options to Nightwatch as an array by using the option `cliArgs`.

```javascript
gulp.task('nightwatch:chrome', function(){
  return gulp.src('gulpfile.js')
    .pipe(nightwatch({
      configFile: 'test/nightwatch.json',
      cliArgs: [ '--env chrome', '--tag sandbox' ]
    }));
});
```

You may use an object instead, if you prefer.

```javascript
gulp.task('nightwatch:chrome', function(){
  return gulp.src('gulpfile.js')
    .pipe(nightwatch({
      configFile: 'test/nightwatch.json',
      cliArgs: {
        env: 'chrome',
        tag: 'sandbox'
      }
    }));
});
```

You can abort Gulp execution when tests fail.

```javascript
gulp.task('nightwatch:chrome', function(){
  return gulp.src('gulpfile.js')
    .pipe(nightwatch({
      configFile: 'test/nightwatch.json',
      abortOnFailure: true
    }));
});
```

## API

### nightwatch(options)

#### options

##### configFile

Type: `String`
Default: `nightwatch.json`

The path to your Nightwatch config

##### cliArgs

Type: `Array` or `Object`
Default: null

##### abortOnFailure

Type: `Bool`
Default: False

Command line options for Nightwatch


[npm-image]: https://img.shields.io/npm/v/gulp-ngwt.svg
[npm-url]: https://www.npmjs.com/package/gulp-ngwt
[travis-image]: https://img.shields.io/travis/dgateles/gulp-ngwt.svg
[travis-url]: https://travis-ci.org/dgateles/gulp-ngwt
