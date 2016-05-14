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
Install Webpack
---------------
When installing Webpack (or any other npm package), you can install globally or locally.  Installing npm packages locally means that packages are installed only in the current project folder, hello-webpack in this case, and are not intended for other apps.  **__I recommend installing npm packages locally as it gives you the freedom to use different versions of packages in different projects.__**

Now let's install Webpack in our local project.  Here is the command:
~~~bash
  mthomas@ubuntu:~/apps/ng2-quickstart$ npm install webpack --save-dev
~~~

When you run this command, you'll see output similar to this:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ npm install webpack --save-dev
npm WARN optional dep failed, continuing fsevents@1.0.12
webpack@1.13.0 node_modules/webpack
├── interpret@0.6.6
├── tapable@0.1.10
├── clone@1.0.2
├── supports-color@3.1.2 (has-flag@1.0.0)
├── async@1.5.2
├── loader-utils@0.2.14 (object-assign@4.0.1, big.js@3.1.3, json5@0.5.0, emojis-list@1.0.1)
├── enhanced-resolve@0.9.1 (graceful-fs@4.1.3, memory-fs@0.2.0)
├── mkdirp@0.5.1 (minimist@0.0.8)
├── optimist@0.6.1 (wordwrap@0.0.3, minimist@0.0.10)
├── acorn@3.1.0
├── memory-fs@0.3.0 (errno@0.1.4, readable-stream@2.1.2)
├── webpack-core@0.6.8 (source-list-map@0.1.6, source-map@0.4.4)
├── watchpack@0.2.9 (graceful-fs@4.1.3, async@0.9.2, chokidar@1.4.3)
├── uglify-js@2.6.2 (uglify-to-browserify@1.0.2, async@0.2.10, source-map@0.5.5, yargs@3.10.0)
└── node-libs-browser@0.5.3 (https-browserify@0.0.0, tty-browserify@0.0.0, constants-browserify@0.0.1, path-browserify@0.0.0, os-browserify@0.1.2, string_decoder@0.10.31, process@0.11.2, punycode@1.4.1, querystring-es3@0.2.1, assert@1.3.0, timers-browserify@1.4.2, domain-browser@1.1.7, events@1.1.0, vm-browserify@0.0.4, util@0.10.3, stream-browserify@1.0.0, console-browserify@1.1.0, http-browserify@1.7.0, readable-stream@1.1.14, url@0.10.3, buffer@3.6.0, browserify-zlib@0.1.4, crypto-browserify@3.2.8)
~~~
_For now, we can safely ignore the warning at the top about the fsevents dependency._  The installation succeded and installed Webpack plus numerous core dependencies.
Install dependencies.  Our app dependencies are specified in package.json.
------------------------------------------------
In order to get our basic app working properly, we will need a couple of _loader_ packages.   Let's install them now:
~~~bash
  mthomas@ubuntu:~/apps/ng2-quickstart$ npm install
~~~
The output will look like this:
~~~bash
mthomas@ubuntu:~/apps/ng2-quickstart$ npm install
css-loader@0.23.1 node_modules/css-loader
├── postcss-modules-extract-imports@1.0.0
├── object-assign@4.0.1
├── postcss-modules-scope@1.0.0
├── postcss-modules-local-by-default@1.0.1
├── postcss-modules-values@1.1.2 (icss-replace-symbols@1.0.2)
├── css-selector-tokenizer@0.5.4 (fastparse@1.1.1, cssesc@0.1.0)
├── loader-utils@0.2.14 (big.js@3.1.3, json5@0.5.0, emojis-list@1.0.1)
├── source-list-map@0.1.6
├── lodash.camelcase@3.0.1 (lodash._createcompounder@3.0.0)
├── postcss@5.0.19 (js-base64@2.1.9, supports-color@3.1.2, source-map@0.5.5)
└── cssnano@3.5.2 (decamelize@1.2.0, postcss-normalize-charset@1.1.0, postcss-discard-empty@2.1.0, indexes-of@1.0.1, postcss-discard-duplicates@2.0.1, postcss-minify-gradients@1.0.1, postcss-reduce-transforms@1.0.3, postcss-convert-values@2.3.4, postcss-reduce-idents@2.3.0, defined@1.0.0, postcss-merge-rules@2.0.8, postcss-discard-comments@2.0.4, postcss-ordered-values@2.1.0, postcss-value-parser@3.3.0, postcss-minify-font-values@1.0.3, postcss-zindex@2.1.1, postcss-unique-selectors@2.0.2, postcss-minify-params@1.0.4, postcss-merge-longhand@2.0.1, postcss-filter-plugins@2.0.0, postcss-merge-idents@2.1.5, postcss-discard-unused@2.2.1, postcss-calc@5.2.1, postcss-minify-selectors@2.0.4, postcss-normalize-url@3.0.7, postcss-colormin@2.2.0, autoprefixer@6.3.6, postcss-svgo@2.1.3)
~~~
Now let's install style-loader:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ npm install style-loader --save-dev
~~~
Here's the output:
~~~bash
mthomas@ubuntu:~/apps/hello-webpack$ npm install style-loader --save-dev
style-loader@0.13.1 node_modules/style-loader
└── loader-utils@0.2.14 (object-assign@4.0.1, big.js@3.1.3, json5@0.5.0, emojis-list@1.0.1)
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
