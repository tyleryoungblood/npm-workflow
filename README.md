# NPM Workflow #

This workflow gives you a boilerplate web app the following features:
- SASS preprossing (via node-sass)
    - css partials using `_partialName`
- require() (via Browserify) 
    - break your JS up into separate modules
- live-reloading (via browser-sync). 

This workflow is loosely based on two tutorials: 
- Scotch.io's [Using NPM as a Build Tool](https://scotch.io/tutorials/using-npm-as-a-build-tool) 
- PentaCode's How To Create A Build System with NPM Scripts [Part 1](https://www.youtube.com/watch?v=yQGkNO_Cot0), [Part 2](https://www.youtube.com/watch?v=Ajt2-fWRwOk), and [Part 3](https://www.youtube.com/watch?v=pkdYYCIzg_I)

## Quick Start
1. Clone repo locally $`git clone git@github.com:tyleryoungblood/npm-workflow.git`
1. Run `npm install` to install the necessary packages into a node_modules folder
1. To run the project locally, type `npm start` in the command line. 
    - A new browser tab should open at localhost:8000 and display "Hello World"
    - `npm start` is shorthand for `npm run start` and runs `npm run watch` and `npm run db` and `npm run serve` concurrently
    - the `-k` in `"start": "concurrently -k ...` tells the [concurrently package](https://www.npmjs.com/package/concurrently) to kill any previously running versions of start, watch, and serve before starting new ones.

After running `npm start` from within the project directory a Hello World page should load at `localhost:8000` or whatever port specified in `bs-config.js`. 

## bs-config.js ##

`bs-config.js` is necessary because lite-server looks for changes to CSS and JS files at the project root level by default. This config file gives you the freedom to have a build or dist directory separate from your src directory (or root).
- `"port": 8000` tells live-server to use localhost:8000 instead of the default port of 3000.
- `"files": ["./build/**/*.{html,htm,css,js}"]` tells live-server to watch for html, css, and JS changes in the build directory. 
- `"server": { "baseDir": "./build" }` tells live-server to serve index.html from within /build and not root.

## NPM Commands ##

1. `npm start` is shorthand for `npm run start` and runs `npm run watch` and `npm run db` and `npm run serve` concurrently
1. `npm run watch` uses nodemon to listen for js and scss changes and runs `build` when changes are made
    - build folder must be ignored using `--ignore build/` to prevent endless build loop!
1. `npm run serve` starts a dev server using [lite-server](https://www.npmjs.com/package/light-server) at port specified in bs-config.json
    - live reloading
    - Browser-sync (included as a sub module of lite-server, so no need to install separately)
    - No need to configure `watch:css` or `watch:js` - live-server will watch all files automatically
1. `npm run db` starts a JSON-server for playing with REST APIs [read more here](https://scotch.io/tutorials/json-server-as-a-fake-rest-api-in-frontend-development)
1. `npm run build:js` will use Browserify minify your JavaScript files and move them to `build/js/app.min.js`
1. `npm run lint` will check JS files in your source folder and detect errors
1. `npm run build:css` will compile your .scss into css
1. `npm test` shorthand for `npm run test` will run Mocha tests
