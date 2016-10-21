### Minify CSS with cssnano.

https://www.npmjs.com/package/gulp-cssnano

```js
var gulp = require('gulp');
var cssnano = require('gulp-cssnano');

gulp.task('default', function() {
    return gulp.src('./main.css')
        .pipe(cssnano())
        .pipe(gulp.dest('./out'));
});

```

### Source Maps

```js
gulp-cssnano supports gulp-sourcemaps:
var gulp = require('gulp');
var cssnano = require('gulp-cssnano');
var sourcemaps = require('gulp-sourcemaps');

gulp.task('default', function () {
    return gulp.src('main.css')
        .pipe(sourcemaps.init())
        .pipe(cssnano())
        .pipe(sourcemaps.write('.'))
        .pipe(gulp.dest('./out'));
});
```
