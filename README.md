# api documentation for  sass (v0.5.0)  [![npm package](https://img.shields.io/npm/v/npmdoc-sass.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sass) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sass.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sass)
#### Syntactically Awesome Stylesheets (compiles to css)

[![NPM](https://nodei.co/npm/sass.png?downloads=true)](https://www.npmjs.com/package/sass)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sass/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-sass_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sass/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sass/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sass/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "TJ Holowaychuk",
        "email": "tj@vision-media.ca"
    },
    "contributors": [
        {
            "name": "Chris Pickel",
            "email": "sfiera@gmail.com"
        }
    ],
    "dependencies": {},
    "description": "Syntactically Awesome Stylesheets (compiles to css)",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "tarball": "https://registry.npmjs.org/sass/-/sass-0.5.0.tgz",
        "shasum": "9dee1183a0f400361f2c5d3453bf2e54705e03f9"
    },
    "engines": {
        "node": "*"
    },
    "keywords": [
        "sass",
        "template",
        "css",
        "view"
    ],
    "main": "./lib/sass",
    "name": "sass",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "version": "0.5.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module sass](#apidoc.module.sass)
1.  [function <span class="apidocSignatureSpan">sass.</span>collect (sass)](#apidoc.element.sass.collect)
1.  [function <span class="apidocSignatureSpan">sass.</span>render (sass, options)](#apidoc.element.sass.render)
1.  object <span class="apidocSignatureSpan">sass.</span>expansions
1.  string <span class="apidocSignatureSpan">sass.</span>version



# <a name="apidoc.module.sass"></a>[module sass](#apidoc.module.sass)

#### <a name="apidoc.element.sass.collect"></a>[function <span class="apidocSignatureSpan">sass.</span>collect (sass)](#apidoc.element.sass.collect)
- description and source-code
```javascript
collect = function (sass) {
  return parse(tokenize(sass))
}
```
- example usage
```shell
...

## Usage

var sass = require('sass')
sass.render('... string of sass ...')
// => '... string of css ...'

sass.collect('... string of sass ...')
// => { selectors: [...], variables: { ... }, mixins: { ... }}

## Comments

// foo
body
  // bar
...
```

#### <a name="apidoc.element.sass.render"></a>[function <span class="apidocSignatureSpan">sass.</span>render (sass, options)](#apidoc.element.sass.render)
- description and source-code
```javascript
render = function (sass, options) {
  options = options || {}
  if (options.cache && !options.filename)
    throw new Error('filename option must be passed when cache is enabled')
  if (options.cache)
    return cache[options.filename]
      ? cache[options.filename]
      : cache[options.filename] = compile(exports.collect(sass).selectors)
  return compile(exports.collect(sass).selectors)
}
```
- example usage
```shell
...
npm:

      $ npm install sass

## Usage

    var sass = require('sass')
    sass.render('... string of sass ...')
    // => '... string of css ...'

    sass.collect('... string of sass ...')
    // => { selectors: [...], variables: { ... }, mixins: { ... }}

## Comments
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
