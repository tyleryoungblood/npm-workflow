# NPM Workflow #

This workflow is loosely based on this Scotch.io's [Using NPM as a Build Tool](https://scotch.io/tutorials/using-npm-as-a-build-tool) tutorial.

## Usage ##

1. Clone repo locally $`git clone git@github.com:tyleryoungblood/npm-workflow.git`
2. `npm start` shorthand for `npm run start` and runs `npm run dev` and `npm run db` concurrently
3. `npm run dev` starts a dev server using [lite-server](https://www.npmjs.com/package/light-server) at localhost:3000
    - live reloading
    - Browser-sync (a sub module of lite-server, so no need to install separately)
    - No need to configure `watch:css` or `watch:js` - live-server will watch all files automatically
4. `npm run db` starts a JSON-server for playing with REST APIs [read more here](https://scotch.io/tutorials/json-server-as-a-fake-rest-api-in-frontend-development)
5. `npm run uglify` will minify your JavaScript files and move them to `dist/js/app.js`
6. `npm run lint` will check JS files in your source folder and detect errors
7. `npm run sass` will compile your .scss into css
8. `npm test` shorthand for `npm run test` will run Mocha tests
