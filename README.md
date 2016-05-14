# hello_webpack bootstrap Ng
Webpack - Bootstrap - Angular

[![Webpack](https://webpack.github.io/assets/what-is-webpack.png)](https://webpack.github.io/)

Summary
-------
Let's put together a basic ("hello world") Webpack + Bootstrap + Angular app.

Development Environment
-----------------------

Here's my development environment:
>  * Ubuntu 14.04
>  * nodejs v4.4.3
>  * npm 2.15.1
>  * various npm packages specified in package.json

Let's get started!

Install NodeJS
--------------
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -

Create an app folder
---------------------
From a shell prompt (I use bash), create a new folder:
~~~bash
  mkdir ng2-quickstart
~~~
Then cd into that folder:
~~~bash
  cd ng2-quickstart
~~~
Verify npm is properly installed
--------------------------------
~~~bash
  npm -v
~~~
If npm is installed properly you will see output like this:
~~~bash
  mthomas@ubuntu:~/apps/ng2-quickstart$ npm -v
  2.15.1
~~~
If you get an error, check the [NPM](https://www.npmjs.com/) documentation and installation guide for help.
Install Webpack and App Dependencies
---------------
When installing Webpack (or any other npm package), you can install globally or locally.  Installing npm packages locally means that packages are installed only in the current project folder, hello-webpack in this case, and are not intended for other apps.  **__I recommend installing npm packages locally as it gives you the freedom to use different versions of packages in different projects.__**

Now let's install Webpack and all the app dependencies.  The app dependencies are specified in package.json.  Here is the command:
~~~bash
npm i
~~~
or
~~~bash
npm install
~~~

When you run this command, you'll see output similar to this:
~~~bash
mthomas@ubuntu:~/apps/ng2-quickstart$ npm i
npm WARN package.json ng2-quickstart@1.0.0 No repository field.
npm WARN peerDependencies The peer dependency sass-loader@* included from font-awesome-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN peerDependencies The peer dependency node-sass@* included from bootstrap-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN peerDependencies The peer dependency resolve-url-loader@* included from bootstrap-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN peerDependencies The peer dependency sass-loader@* included from bootstrap-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN peerDependencies The peer dependency url-loader@* included from bootstrap-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN peerDependencies The peer dependency node-sass@^3.4.2 included from sass-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN optional dep failed, continuing fsevents@1.0.12
npm WARN peerDependencies The peer dependency file-loader@* included from url-loader will no
npm WARN peerDependencies longer be automatically installed to fulfill the peerDependency 
npm WARN peerDependencies in npm 3+. Your application will need to depend on it explicitly.
npm WARN optional dep failed, continuing fsevents@1.0.12
/
> node-sass@3.7.0 install /home/mthomas/apps/ng2-quickstart/node_modules/node-sass
> node scripts/install.js

Binary downloaded and installed at /home/mthomas/apps/ng2-quickstart/node_modules/node-sass/vendor/linux-x64-46/binding.node

> node-sass@3.7.0 postinstall /home/mthomas/apps/ng2-quickstart/node_modules/node-sass
> node scripts/build.js

"/home/mthomas/apps/ng2-quickstart/node_modules/node-sass/vendor/linux-x64-46/binding.node" exists. 
 testing binary.
Binary is fine; exiting.
zone.js@0.6.12 node_modules/zone.js

style-loader@0.13.1 node_modules/style-loader
└── loader-utils@0.2.15 (object-assign@4.1.0, emojis-list@2.0.1, big.js@3.1.3, json5@0.5.0)

font-awesome@4.6.1 node_modules/font-awesome

@angular/upgrade@2.0.0-rc.1 node_modules/@angular/upgrade

reflect-metadata@0.1.3 node_modules/reflect-metadata

imports-loader@0.6.5 node_modules/imports-loader
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
└── source-map@0.1.43 (amdefine@1.0.0)

@angular/platform-browser-dynamic@2.0.0-rc.1 node_modules/@angular/platform-browser-dynamic

angular2-in-memory-web-api@0.0.7 node_modules/angular2-in-memory-web-api
└── es6-shim@0.35.1

extract-text-webpack-plugin@1.0.1 node_modules/extract-text-webpack-plugin
├── async@1.5.2
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
└── webpack-sources@0.1.2 (source-map@0.5.6, source-list-map@0.1.6)

tether@1.3.2 node_modules/tether

postcss-loader@0.9.1 node_modules/postcss-loader
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
└── postcss@5.0.21 (js-base64@2.1.9, supports-color@3.1.2, source-map@0.5.6)

bootstrap@3.3.6 node_modules/bootstrap

jquery@2.2.3 node_modules/jquery

@angular/http@2.0.0-rc.1 node_modules/@angular/http

@angular/router@2.0.0-rc.1 node_modules/@angular/router

@angular/router-deprecated@2.0.0-rc.1 node_modules/@angular/router-deprecated

css-loader@0.23.1 node_modules/css-loader
├── postcss-modules-extract-imports@1.0.1
├── postcss-modules-scope@1.0.1
├── object-assign@4.1.0
├── postcss-modules-local-by-default@1.0.1
├── loader-utils@0.2.15 (emojis-list@2.0.1, big.js@3.1.3, json5@0.5.0)
├── postcss-modules-values@1.1.3 (icss-replace-symbols@1.0.2)
├── css-selector-tokenizer@0.5.4 (fastparse@1.1.1, cssesc@0.1.0)
├── source-list-map@0.1.6
├── lodash.camelcase@3.0.1 (lodash._createcompounder@3.0.0)
├── postcss@5.0.21 (js-base64@2.1.9, supports-color@3.1.2, source-map@0.5.6)
└── cssnano@3.5.2 (decamelize@1.2.0, postcss-normalize-charset@1.1.0, postcss-minify-gradients@1.0.1, postcss-reduce-transforms@1.0.3, postcss-discard-empty@2.1.0, postcss-discard-duplicates@2.0.1, indexes-of@1.0.1, postcss-convert-values@2.3.4, postcss-merge-rules@2.0.8, postcss-reduce-idents@2.3.0, postcss-discard-comments@2.0.4, defined@1.0.0, postcss-value-parser@3.3.0, postcss-ordered-values@2.1.1, postcss-minify-font-values@1.0.5, postcss-filter-plugins@2.0.0, postcss-zindex@2.1.1, postcss-discard-unused@2.2.1, postcss-minify-params@1.0.4, postcss-unique-selectors@2.0.2, postcss-merge-longhand@2.0.1, postcss-merge-idents@2.1.6, postcss-calc@5.2.1, postcss-normalize-url@3.0.7, postcss-minify-selectors@2.0.5, postcss-colormin@2.2.0, postcss-svgo@2.1.3)

file-loader@0.8.5 node_modules/file-loader
└── loader-utils@0.2.15 (object-assign@4.1.0, emojis-list@2.0.1, big.js@3.1.3, json5@0.5.0)

url-loader@0.5.7 node_modules/url-loader
├── mime@1.2.11
└── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)

resolve-url-loader@1.4.3 node_modules/resolve-url-loader
├── camelcase@1.2.1
├── rework-visit@1.0.0
├── convert-source-map@1.2.0
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
├── lodash.defaults@3.1.2 (lodash.restparam@3.6.1, lodash.assign@3.2.0)
├── source-map@0.1.43 (amdefine@1.0.0)
└── rework@1.0.1 (convert-source-map@0.3.5, css@2.2.1)

bootstrap-loader@1.0.9 node_modules/bootstrap-loader
├── escape-regexp@0.0.1
├── strip-json-comments@1.0.4
├── semver@5.1.0
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
├── chalk@1.1.3 (escape-string-regexp@1.0.5, ansi-styles@2.2.1, supports-color@2.0.0, has-ansi@2.0.0, strip-ansi@3.0.1)
├── resolve@1.1.7
└── js-yaml@3.6.1 (esprima@2.7.2, argparse@1.0.7)

@angular/platform-browser@2.0.0-rc.1 node_modules/@angular/platform-browser

bootstrap-sass@3.3.6 node_modules/bootstrap-sass

@angular/common@2.0.0-rc.1 node_modules/@angular/common

webpack@1.13.0 node_modules/webpack
├── interpret@0.6.6
├── tapable@0.1.10
├── async@1.5.2
├── clone@1.0.2
├── supports-color@3.1.2 (has-flag@1.0.0)
├── loader-utils@0.2.15 (object-assign@4.1.0, big.js@3.1.3, emojis-list@2.0.1, json5@0.5.0)
├── enhanced-resolve@0.9.1 (graceful-fs@4.1.4, memory-fs@0.2.0)
├── acorn@3.1.0
├── mkdirp@0.5.1 (minimist@0.0.8)
├── optimist@0.6.1 (wordwrap@0.0.3, minimist@0.0.10)
├── memory-fs@0.3.0 (errno@0.1.4, readable-stream@2.1.2)
├── webpack-core@0.6.8 (source-map@0.4.4, source-list-map@0.1.6)
├── uglify-js@2.6.2 (async@0.2.10, uglify-to-browserify@1.0.2, source-map@0.5.6, yargs@3.10.0)
├── watchpack@0.2.9 (graceful-fs@4.1.4, async@0.9.2, chokidar@1.5.0)
└── node-libs-browser@0.5.3 (https-browserify@0.0.0, tty-browserify@0.0.0, constants-browserify@0.0.1, path-browserify@0.0.0, punycode@1.4.1, string_decoder@0.10.31, os-browserify@0.1.2, process@0.11.3, assert@1.3.0, domain-browser@1.1.7, querystring-es3@0.2.1, timers-browserify@1.4.2, stream-browserify@1.0.0, events@1.1.0, vm-browserify@0.0.4, console-browserify@1.1.0, util@0.10.3, readable-stream@1.1.14, url@0.10.3, http-browserify@1.7.0, buffer@3.6.0, browserify-zlib@0.1.4, crypto-browserify@3.2.8)

@angular/compiler@2.0.0-rc.1 node_modules/@angular/compiler

@angular/core@2.0.0-rc.1 node_modules/@angular/core

autoprefixer@6.3.6 node_modules/autoprefixer
├── normalize-range@0.1.2
├── num2fraction@1.2.2
├── postcss-value-parser@3.3.0
├── browserslist@1.3.1
├── postcss@5.0.21 (js-base64@2.1.9, supports-color@3.1.2, source-map@0.5.6)
└── caniuse-db@1.0.30000466

concurrently@2.1.0 node_modules/concurrently
├── commander@2.6.0
├── cross-spawn@0.2.9 (lru-cache@2.7.3)
├── chalk@0.5.1 (ansi-styles@1.1.0, escape-string-regexp@1.0.5, supports-color@0.2.0, strip-ansi@0.3.0, has-ansi@0.1.0)
├── bluebird@2.9.6
├── moment@2.13.0
├── rx@2.3.24
└── lodash@4.12.0

lite-server@2.2.0 node_modules/lite-server
├── connect-history-api-fallback@1.2.0
├── minimist@1.2.0
├── connect-logger@0.0.1 (moment@2.13.0)
├── lodash@4.12.0
└── browser-sync@2.12.8 (ucfirst@1.0.0, emitter-steward@1.0.0, dev-ip@1.0.1, immutable@3.7.6, opn@3.0.3, ua-parser-js@0.7.10, qs@6.1.0, browser-sync-client@2.4.2, http-proxy@1.13.2, portscanner@1.0.0, connect@3.4.1, serve-static@1.10.2, resp-modifier@6.0.1, micromatch@2.3.7, chokidar@1.4.3, fs-extra@0.26.7, socket.io@1.4.5, serve-index@1.7.3, yargs@4.4.0, localtunnel@1.8.1, bs-recipes@1.2.2, easy-extender@2.3.2, eazy-logger@2.1.3, lodash@4.10.0, browser-sync-ui@0.5.19)

rxjs@5.0.0-beta.6 node_modules/rxjs

node-sass@3.7.0 node_modules/node-sass
├── get-stdin@4.0.1
├── async-foreach@0.1.3
├── in-publish@2.0.0
├── chalk@1.1.3 (escape-string-regexp@1.0.5, supports-color@2.0.0, ansi-styles@2.2.1, strip-ansi@3.0.1, has-ansi@2.0.0)
├── nan@2.3.3
├── mkdirp@0.5.1 (minimist@0.0.8)
├── glob@7.0.3 (path-is-absolute@1.0.0, inherits@2.0.1, once@1.3.3, inflight@1.0.4, minimatch@3.0.0)
├── cross-spawn-async@2.2.2 (lru-cache@4.0.1, which@1.2.8)
├── meow@3.7.0 (decamelize@1.2.0, map-obj@1.0.1, trim-newlines@1.0.0, object-assign@4.1.0, camelcase-keys@2.1.0, minimist@1.2.0, loud-rejection@1.3.0, redent@1.0.0, normalize-package-data@2.3.5, read-pkg-up@1.0.1)
├── gaze@1.0.0 (globule@0.2.0)
├── request@2.72.0 (aws-sign2@0.6.0, tunnel-agent@0.4.3, forever-agent@0.6.1, oauth-sign@0.8.2, caseless@0.11.0, is-typedarray@1.0.0, stringstream@0.0.5, aws4@1.4.1, isstream@0.1.2, json-stringify-safe@5.0.1, extend@3.0.0, tough-cookie@2.2.2, node-uuid@1.4.7, qs@6.1.0, combined-stream@1.0.5, mime-types@2.1.11, form-data@1.0.0-rc4, hawk@3.1.3, bl@1.1.2, http-signature@1.1.1, har-validator@2.0.6)
├── sass-graph@2.1.1 (glob@6.0.4, yargs@3.32.0, lodash@4.12.0)
└── node-gyp@3.3.1 (graceful-fs@4.1.4, semver@5.1.0, osenv@0.1.3, nopt@3.0.6, minimatch@1.0.0, which@1.2.8, tar@2.2.1, glob@4.5.3, rimraf@2.5.2, fstream@1.0.9, npmlog@2.0.3, path-array@1.0.1)

sass-loader@3.2.0 node_modules/sass-loader
├── object-assign@4.1.0
├── async@1.5.2
└── loader-utils@0.2.15 (emojis-list@2.0.1, big.js@3.1.3, json5@0.5.0)

font-awesome-loader@0.0.1 node_modules/font-awesome-loader
~~~
Let's take a quick look around at what we've installed.  A quick directory listing shows that a newly created node modules folder:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ ls -lF
total 24
drwxrwxr-x 6 mthomas mthomas 4096 Apr 30 15:13 node_modules/
~~~
Looking inside that folder we see the npm packages we've installed:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ ls -lF node_modules/
total 12
drwxrwxr-x 4 mthomas mthomas 4096 Apr 30 15:08 css-loader/
drwxrwxr-x 3 mthomas mthomas 4096 Apr 30 15:13 style-loader/
drwxrwxr-x 8 mthomas mthomas 4096 Apr 30 14:57 webpack/
~~~
The basic requirements for our hello_webpack app are now in place.  Let's build it!
Make /js and /css folders
-------------------------
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ mkdir css
~~~
and...
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ mkdir js
~~~
Create and edit js/first.js
---------------------------
Let's add/edit the file js/first.js
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ vim js/first.js
~~~
Add the following line to the very top of js/first.js
~~~javascript
  document.write("hello first.js");
~~~
The save and close js/first.js.
Use Webpack to Build bundle.js
------------------------------
Now we will use our local Webpack installation to 'compile' js/first.js.  The output of the compilation will create bundle.js.
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ ./node_modules/.bin/webpack ./js/first.js  bundle.js
~~~
You should see an output like this:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ ./node_modules/.bin/webpack ./js/first.js  bundle.js 
Hash: a0c52be0b7efa554daec
Version: webpack 1.13.0
Time: 37ms
    Asset     Size  Chunks             Chunk Names
bundle.js  1.51 kB       0  [emitted]  main
   [0] ./js/first.js 125 bytes {0} [built]
~~~
You should now see bundle.js in your app folder like this:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ ls -lF
total 28
-rw-rw-r-- 1 mthomas mthomas 1515 Apr 30 15:54 bundle.js
drwxrwxr-x 2 mthomas mthomas 4096 Apr 30 12:24 css/
drwxrwxr-x 2 mthomas mthomas 4096 Apr 30 13:34 js/
drwxrwxr-x 6 mthomas mthomas 4096 Apr 30 15:13 node_modules/
~~~
Looking inside bundle.js, you will see the compiled Javascript, including the contents of js/first.js:
~~~javascript
/******/ (function(modules) { // webpackBootstrap
/******/ 	// The module cache
/******/ 	var installedModules = {};

/******/ 	// The require function
/******/ 	function __webpack_require__(moduleId) {

/******/ 		// Check if module is in cache
/******/ 		if(installedModules[moduleId])
/******/ 			return installedModules[moduleId].exports;

/******/ 		// Create a new module (and put it into the cache)
/******/ 		var module = installedModules[moduleId] = {
/******/ 			exports: {},
/******/ 			id: moduleId,
/******/ 			loaded: false
/******/ 		};

/******/ 		// Execute the module function
/******/ 		modules[moduleId].call(module.exports, module, module.exports, __webpack_require__);

/******/ 		// Flag the module as loaded
/******/ 		module.loaded = true;

/******/ 		// Return the exports of the module
/******/ 		return module.exports;
/******/ 	}


/******/ 	// expose the modules object (__webpack_modules__)
/******/ 	__webpack_require__.m = modules;

/******/ 	// expose the module cache
/******/ 	__webpack_require__.c = installedModules;

/******/ 	// __webpack_public_path__
/******/ 	__webpack_require__.p = "";

/******/ 	// Load entry module and return exports
/******/ 	return __webpack_require__(0);
/******/ })
/************************************************************************/
/******/ ([
/* 0 */
/***/ function(module, exports) {

	document.write("hello first.js");
	


/***/ }
/******/ ]);
~~~
Now let's create a quick index.html file to test our new bundle.js.
Create/edit index.html
----------------------
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ vim index.html
~~~
Add the following html to index.html:
~~~html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
  </head>
  <body>
    <script type="text/javascript" src="bundle.js" charset="utf-8"></script>
  </body>
</html>
~~~
Save and close index.html and open in a browser:
![browser view](images/index-view.JPG)
**Success!**
Next, let's add a very simple css style sheet to out app.
Create and edit css/style.css
---------------------------
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ vim css/style.css
~~~
Add the following code to css/style.css and save.
~~~css
body {
    background: green;
}
~~~
Add css/style.css to bundle.js
------------------------------
We want Weback to add css/style.css to bundle.js so the style contents can be applied to index.html.  Edit **js/first.js**, and add the require statement below.
~~~javascript
document.write("hello first.js");
require("!style!css!../css/style.css");
~~~
Save and close js/first.js.

Recompile first.js
------------------
~~~bash
  mthomas@ubuntu:~/apps/hello-webpack$ ./node_modules/.bin/webpack ./js/first.js  bundle.js
~~~
Now open/refresh your browser page with index.html and you should see our same text but with a green background:
![browser view green](images/index-view-green.JPG)

And we're done!
