# NPM Workflow #

This workflow is loosely based on this Scotch.io's [Using NPM as a Build Tool](https://scotch.io/tutorials/using-npm-as-a-build-tool) tutorial.

## Quick Start
1. Clone repo locally $`git clone git@github.com:tyleryoungblood/npm-workflow.git`
2. `npm start` shorthand for `npm run start` and runs `npm run watch` and `npm run db` concurrently

## NPM Commands ##

1. `npm start` shorthand for `npm run start` and runs `npm run watch` and `npm run db` concurrently
2. `npm run watch` uses nodemon to listen for js and css changes and runs `build` and `serve` when changes are made
    - build folder must be ignored using `--ignore build/` to prevent endless build loop!
4. `npm run serve` starts a dev server using [lite-server](https://www.npmjs.com/package/light-server) at localhost:3000
    - live reloading
    - Browser-sync (a sub module of lite-server, so no need to install separately)
    - No need to configure `watch:css` or `watch:js` - live-server will watch all files automatically
5. `npm run db` starts a JSON-server for playing with REST APIs [read more here](https://scotch.io/tutorials/json-server-as-a-fake-rest-api-in-frontend-development)
6. `npm run build:js` will use Browserify minify your JavaScript files and move them to `build/js/app.min.js`
7. `npm run lint` will check JS files in your source folder and detect errors
8. `npm run build:css` will compile your .scss into css
9. `npm test` shorthand for `npm run test` will run Mocha tests
