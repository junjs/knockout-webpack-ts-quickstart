# knockout-webpack-ts-quickstart
Quickstart project for knockout.js + TypeScript with Webpack2.

[![npm](https://img.shields.io/npm/v/knockout-webpack-ts-quickstart.svg)](https://www.npmjs.com/package/knockout-webpack-ts-quickstart)
[![GitHub release](https://img.shields.io/github/release/shellyln/knockout-webpack-ts-quickstart.svg)](https://github.com/shellyln/knockout-webpack-ts-quickstart/releases)
[![Travis](https://img.shields.io/travis/shellyln/knockout-webpack-ts-quickstart/master.svg)](https://travis-ci.org/shellyln/knockout-webpack-ts-quickstart)
[![GitHub forks](https://img.shields.io/github/forks/shellyln/knockout-webpack-ts-quickstart.svg?style=social&label=Fork)](https://github.com/shellyln/knockout-webpack-ts-quickstart/fork)
[![GitHub stars](https://img.shields.io/github/stars/shellyln/knockout-webpack-ts-quickstart.svg?style=social&label=Star)](https://github.com/shellyln/knockout-webpack-ts-quickstart)

---

### Features
* Compile TypeScript source and output as single file with source map.
* Compile SCSS, do auto-prefixing (PostCSS), and output as single CSS file with source map.
* Run unit tests ([jasmine](https://jasmine.github.io/)).
* Include CI configurations
  ([Travis CI](https://travis-ci.org/),
   [bitbucket pipelines](https://www.atlassian.com/software/bitbucket/features/pipelines),
   [Wercker](http://www.wercker.com/),
   [AWS CodeBuild](https://aws.amazon.com/codebuild/)).
* Include Visual Studio Code debugger and tasks configurations.




# Usage (Starting your project)
1. Fork and clone me.
1. Edit package informations of `package.json`.  
   Don't remember to change repository url, author, homepage.
1.  Edit library name and output file name of `webpack.config.js`.  
    ```javascript
    // [Node-single-js-file]: Packing a Node single Javascript file.
    {
        entry: {
            // TODO: YOU SHOULD REPLACE THE LIBRARY OUTPUT NAME!
            <your-output-name>: path.resolve(__dirname, 'src/index.ts')
        },
        output: {
            // TODO: YOU SHOULD REPLACE THE LIBRARY NAME!
            library: '<your-library-name>',
            ...
        },
        module: {
            rules: [{
                test: /\.tsx?$/,
                ...

                // TODO: YOU SHOULD REPLACE THE PACKAGE NAME!
                // exclude 'node_module' directory except myself (refered from other packages)
                exclude: /node_modules[\/\\](?!knockout-webpack-ts-quickstart).*$/
            }, {
                test: /\.jsx?$/,
                ...

                // TODO: YOU SHOULD REPLACE THE PACKAGE NAME!
                // exclude 'node_module' directory except myself (refered from other packages)
                exclude: /node_modules[\/\\](?!knockout-webpack-ts-quickstart).*$/
            }, {
            ...
    },

    // [Browser-single-js-file]: Packing a library Javascript file.
    {
        entry: {
            // TODO: YOU SHOULD REPLACE THE LIBRARY OUTPUT NAME!
            <your-output-name>: path.resolve(__dirname, 'src/index.ts')
        },
        output: {
            // TODO: YOU SHOULD REPLACE THE LIBRARY NAME!
            library: '<your-library-name>',
            ...
        },
        module: {
            rules: [{
                test: /\.tsx?$/,
                ...

                // TODO: YOU SHOULD REPLACE THE PACKAGE NAME!
                // exclude 'node_module' directory except myself (refered from other packages)
                exclude: /node_modules[\/\\](?!knockout-webpack-ts-quickstart).*$/
            }, {
                test: /\.jsx?$/,
                ...

                // TODO: YOU SHOULD REPLACE THE PACKAGE NAME!
                // exclude 'node_module' directory except myself (refered from other packages)
                exclude: /node_modules[\/\\](?!knockout-webpack-ts-quickstart).*$/
            }, {
            ...
    },
    ```
1. Write your code.
1. and build it.  
   ```sh
   npm run build
   npm test
   ```




# Compile SCSS Stylesheets to single CSS file.
1. Clone me:  
   ```sh
   git clone shellyln/knockout-webpack-ts-quickstart.git
   ```
1. Build me:
   ```sh
   npm run build
   npm test
   ```
1. Copy `dist/style.min.css` and `dist/style.min.css.map` to your site.
1. and use:

app.html
```html
<head>
    <link rel="stylesheet" type="text/css" href="path/to/style.min.css">
</head>
```




# Debugging with Webpack
1. `npm start`
1. Run browser's devtools.
1. Fix anything and save it.
1. Go back to line 2.




# Directory structure
* /bin/ : Output directory of Node module javascript file (CommonJS) that build with tsc.
* /dist/ : Output directory of distribution javascript single file (AMD ; for browsers) and stylesheet single file that build+packed by Webpack.
* /declarations/ : Output directory of TypeScript declaration.
* /spec/ : Directory of [jasmine](https://jasmine.github.io/) configurations.
* /src/index.ts : Library main file.
* /src/app.ts : Entry point file.
* /src/app/ : Application source files.
* /src/app/components : Components source files.
* /src/lib/ : Directory of library program codes.
* /src/spec/ : Directory of unit test codes. We use [jasmine](https://jasmine.github.io/).
* /src/assets/scss/ : Directory of stylesheet source.
* /src/assets/ : Assets packed by Webpack.
* /.babelrc : Babel configuration.
* /.gitignore : git ignore list.
* /.npmignore : NPM ignore list.
* /package.json : NPM package configuration.
* /tsconfig.json : [TypeScript compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html) for Node module output. it also uses for IDEs' error checking and coding assistance.
* /tsconfig-webpack-dist.json : [TypeScript compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html) for distribution single file output.
* /webpack.config.js : [Webpack2 build configuration](https://webpack.js.org/configuration/).
* /.travis.yml : [Travis CI](https://travis-ci.org/) test and deploying pipeline configuration.
* /bitbucket-pipelines.yml : [bitbucket pipelines](https://www.atlassian.com/software/bitbucket/features/pipelines) test and deploying pipeline configuration.
* /bitbucket-heroku-deploy.sh : bitbucket test and deploying pipeline helper shell script.
* /wercker.yml : [Wercker](http://www.wercker.com/) test and deploying pipeline configuration.
* /buildspec.yml : AWS CodeBuild test and deploying pipeline configuration.
* /buildspec-heroku-pre-deploy.sh : AWS CodeBuild test and deploying pipeline helper shell script.
* /buildspec-heroku-deploy.sh : AWS CodeBuild test and deploying pipeline helper shell script.




# NPM scripts
* build : Build for production.
* rebuild : Clean all output and build for production.
* build:node:dev : Build Node module output (CommonJS) for develop.
* build:node:prod : Build Node module output (CommonJS) for production.
* build:dist:dev : Build distribution output (AMD) for develop.
* build:dist:prod : Build distribution output (AMD) for production.
* clean : Clean all output.
* test : Run unit tests.
* start : Run codes for debugging (bin/app.js).
* watch : Build distribution output and watch continuously.




# License
MIT
