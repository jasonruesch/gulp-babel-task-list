[gulp](http://gulpjs.com)-babel-task-list
==============

gulp-babel-task-list is a [gulp](http://gulpjs.com) task that lists all tasks in gulpfile.babel.js along with their comments.

    
gulpfile.babel.js
-----------

```javascript

    var gulp = require('gulp');
    
    require('gulp-babel-task-list')(gulp);
    
    // this task is a dummy task
    gulp.task('some-task', function() {
        console.log('this is some-task');
    });

    // now, this one is the second dummy task
    gulp.task('the-second-task', ['some-task'], function() {
        console.log('uuuu, a second task :)');
    });
```
command line
------------

    $ gulp task-list

    Task name         Description                                         Dependencies
    some-task         this task is a dummy task
    the-secont-task   now, this one is the second dummy task              some-task


Ignore a task to be displayed
-----------------------------

```javascript

    var gulp = require('gulp');

    require('gulp-babel-task-list')(gulp, ['private-task']);

    // this task is a dummy task
    gulp.task('some-task', function() {
        console.log('this is some-task');
    });

    // this is a private task
    gulp.task('private-task', function() {
        console.log('This task is private');
    });
```
command line
------------

    $ gulp task-list

    Task name         Description                                         Dependencies
    some-task         this task is a dummy task
