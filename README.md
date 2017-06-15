# lernetz-stylus-gulp-task
A gulp task that compiles [stylus](http://stylus-lang.com/) files, applies the autoprefixer postcss processor, generates sourcemaps and a minified version.

## Usage
The following example will compile all the stylus files given as `src` into to output folder `public` with the base name `demo`.
It creates the following files:
* demo.css - the uncompressed css file including the sourcemap definition
* demo.min.css - the minified css file

```javascript
var gulp = require('gulp');
var cssTask = require( 'lernetz-stylus-gulp-task' );

gulp.task( 'css', cssTask( { name:'demo', desc:'public', src:'stylus/main.styl' } ) );
```

## Options
The task accepts an parameter object with the following attributes:
```javascript
{
    name: 'name', // the file name of the generated files
    src: 'src/**.ts', // the source parameter for the gulp.src( .. )
    dest: 'public', // the destination used in gulp.dest( .. )
    stylus: {}, // options for the stylus compiler used in gulp-stylus: https://www.npmjs.com/package/gulp-stylus#options
	prefixer: { cascade: true } // options for the gulp-autoprefixer: https://github.com/sindresorhus/gulp-autoprefixer#options
}
```
