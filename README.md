grunt-durandal
==============

Grunt task to build Durandal projects using a custom require config with a custom almond

## Getting Started

Install this grunt plugin next to your project's gruntfile with: `npm install grunt-durandal --save-dev`

Then add this line to your project's `Gruntfile.js` :

```javascript
grunt.loadNpmTasks('grunt-durandal');
```

Then specify your config: ([more informations][doc-options])

```javascript
grunt.initConfig({
    durandal: {
        dist: {
            src: 'app/**/*.*',
            options: {
                baseUrl: "app/",
                mainPath: "app/main.js",
                out: "app/main-built.js",

                uglify2: {
                    compress: {
                        global_defs: {
                            DEBUG: false
                        }
                    }
                }
            }
        }
    }
});
```

Using the configuration above, consider the following app structure :

* App
    * durandal 
        * all durandal files
    * viewmodels
        * shell.js
        * home.js
    * views
        * shell.html
        * home.html
    * main.js

After running the grunt task, a main-built file will be created in your app folder.
This file contains a custom almond, and all your modules inlined (views included as text!...)

## Release History
* 0.0.1 Initial Release

[grunt]: https://github.com/gruntjs/grunt
[doc-options]: https://github.com/spatools/grunt-durandal/wiki/Task-Options