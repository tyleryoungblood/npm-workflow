# NPM Workflow #

This workflow is loosely based on this Scotch.io's [Using NPM as a Build Tool](https://scotch.io/tutorials/using-npm-as-a-build-tool) tutorial.

## Usage ##

1. Clone repo locally $`git clone git@github.com:tyleryoungblood/npm-workflow.git .`
2. `npm run dev` starts a dev server using [lite-server](https://www.npmjs.com/package/light-server) at localhost:3000
    - live reloading
    - Browser-sync (a sub module of lite-server, so no need to install separately)
    - No need to configure `watch:css` or `watch:js` - live-server will watch all files automatically. 
3.