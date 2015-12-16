# Gulp Angular Components

*NOTE:* This is more than just a gulp plugin, it is part of a very cool architecture
for developing Angular.js apps.

Benefits:

- Good, stable and most of all SIMPLE structure
- Faster development, believe me ;)
- Uses [John Papa](https://github.com/johnpapa/angular-styleguide) naming conventions
- Never fucking write boilerplate code anymore like: ```javascript angular.module('demo').directive('dashboard', myDirectiveFunction);``` etc.

# Install

```
npm install gulp-angular-components --save
```

# Usage

- Create a directory in your app / src directory named ```components```

gulpfile.js

```javascript
var gulp = require('gulp');
var sourcemaps = require('gulp-sourcemaps');
var angularComponents = require('gulp-angular-components');

gulp.task('components', function () {
  return gulp
    .src('src/components/*')
    .pipe(sourcemaps.init())
      .pipe(angularComponents({
        moduleName: 'myApp'
      }))
    .pipe(sourcemaps.write())
    .pipe(gulp.dest('.tmp/scripts'));
});
```

src/components/dashboard/dashboard.directive.js
```javascript
function dashboard () {
  return {
    restrict: 'E',
    templateUrl: 'dashboard/dashboard.html',
    
  }
}
```

# Options
