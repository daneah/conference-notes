# Confident Asset Deployments With Webpack and Django
## Scott Burns

### Ideas

* http://webpack.github.io

### Confident Asset Deployments

* Deployments - changes, features, fixes
* Assets - JavaScript, CSS, images
* Confident
    * easy to begin
    * reversible
    * fast
    * autumated
    * few 3rd parties
    * tested

### Why Now?

* Toolchains have improved
* Communities move at different speeds
* Build bridges, not wrappers (collectstatic customization is a "wrapper")

### How Does it Look?

* Webpack
* `webpack.config.js`
    * plugins, input/output definitions, etc.
* `webpack --config webpack.config.js`
* `webpack-stats.json`
    * status, chunks, output
* staticfiles + webpack-loader, which reads `webpack-stats.json`
