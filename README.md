# gulp-pdflatex2
[![npm](https://img.shields.io/npm/v/gulp-pdflatex2.svg)](https://www.npmjs.com/package/gulp-pdflatex2)
[![npm](https://img.shields.io/npm/l/gulp-pdflatex2.svg)](https://spdx.org/licenses/MIT)
[![npm](https://img.shields.io/npm/dt/gulp-pdflatex2.svg)]([![npm](https://img.shields.io/npm/v/npm.svg)](https://www.npmjs.com/package/gulp-pdflatex2))
[![GitHub pull requests](https://img.shields.io/github/issues-pr/omgimanerd/gulp-pdflatex2.svg)](https://github.com/omgimanerd/gulp-pdflatex2/pulls)
[![GitHub issues](https://img.shields.io/github/issues/omgimanerd/gulp-pdflatex2.svg)](https://github.com/omgimanerd/gulp-pdflatex2/issues)

[![GitHub watchers](https://img.shields.io/github/watchers/omgimanerd/gulp-pdflatex2.svg?style=social&label=Watch)](https://github.com/omgimanerd/gulp-pdflatex2/watchers)
[![GitHub forks](https://img.shields.io/github/forks/omgimanerd/gulp-pdflatex2.svg?style=social&label=Fork)](https://github.com/omgimanerd/gulp-pdflatex2/fork)

gulp-pdflatex2 is a wrapper around `pdflatex` for compiling .tex files into
.pdf files.

## Installation
```
npm install --save gulp-pdflatex2
```

## Usage
```javascript
// gulp-rename is not required, but very helpful for redirecting your
// .tex files to a specific output directory.
var gulp = require('gulp');
var rename = require('gulp-rename');
var pdflatex2 = require('gulp-pdflatex2');

gulp.task('latex', function() {
  return gulp.src('./*.tex')
    .pipe(pdflatex({
      verbose: true,
      TEXINPUTS: ['./path/to/cls']
    }))
    .pipe(rename(function(path) {
      path.dirname += '/output';
    }))
    .pipe(gulp.dest('./'));
});
```

## Options
- `verbose`: optional, will output all stdout from pdflatex if there is an
  error, defaults to false.
- `TEXINPUTS`: optional, pass an array of directories for pdflatex to look
  in for files, useful if you have external class files.

## Author
[![Libraries.io for GitHub](https://img.shields.io/badge/Alvin%20Lin-omgimanerd-blue.svg)](http://omgimanerd.tech)
[![Twitter Follow](https://img.shields.io/twitter/follow/omgimanerd.svg?style=social&label=Follow)](https://twitter.com/omgimanerd)
[![GitHub followers](https://img.shields.io/github/followers/omgimanerd.svg?style=social&label=Follow)](https://github.com/omgimanerd)
