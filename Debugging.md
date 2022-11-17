# if something doesn't work
- open dev tools
- open console
- if err : fix it / google 
- else it is a logical error so go to sources tab
- go to webpack click on line numbers of the lines you want to debug.
- repeat the thing you were doing and this time see your code executing line by line with all the states.
# alternative
- you can also search for code in main.bundle,
- if you put breakpoint on a line in bundle it will take you to the ts/js code (using sourcemaps)
- sourcemaps map your bundled/minified js to the ts/js in your code
- sourcemaps are stripped off in prod build.
