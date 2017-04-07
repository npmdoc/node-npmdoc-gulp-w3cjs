# api documentation for  [gulp-w3cjs (v1.3.0)](https://github.com/callumacrae/gulp-w3cjs)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-w3cjs.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-w3cjs) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-w3cjs.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-w3cjs)
#### A Gulp wrapper for w3cjs to validate your HTML

[![NPM](https://nodei.co/npm/gulp-w3cjs.png?downloads=true)](https://www.npmjs.com/package/gulp-w3cjs)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-w3cjs/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-w3cjs_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-w3cjs/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-w3cjs/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-w3cjs/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Callum Macrae",
        "email": "callum@macr.ae",
        "url": "https://github.com/callumacrae"
    },
    "bugs": {
        "url": "https://github.com/callumacrae/gulp-w3cjs/issues"
    },
    "dependencies": {
        "gulp-util": "^3.0.5",
        "through2": "^2.0.0",
        "w3cjs": "^0.3.0"
    },
    "description": "A Gulp wrapper for w3cjs to validate your HTML",
    "devDependencies": {
        "mocha": "^2.2.5",
        "should": "^6.0.3"
    },
    "directories": {},
    "dist": {
        "shasum": "bdb447c32ecd2febec9be167e93e07b95244ab65",
        "tarball": "https://registry.npmjs.org/gulp-w3cjs/-/gulp-w3cjs-1.3.0.tgz"
    },
    "engines": {
        "node": ">=0.10.0",
        "npm": ">=1.2.10"
    },
    "gitHead": "06384490bfc786330a507a46a6eafa35ae897272",
    "homepage": "https://github.com/callumacrae/gulp-w3cjs",
    "keywords": [
        "gulpplugin",
        "html",
        "validate",
        "validation",
        "w3c"
    ],
    "licenses": [
        {
            "type": "MIT"
        }
    ],
    "main": "./index.js",
    "maintainers": [
        {
            "name": "callumacrae",
            "email": "callum@macr.ae"
        }
    ],
    "name": "gulp-w3cjs",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/callumacrae/gulp-w3cjs.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "1.3.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-w3cjs](#apidoc.module.gulp-w3cjs)
1.  [function <span class="apidocSignatureSpan">gulp-w3cjs.</span>reporter ()](#apidoc.element.gulp-w3cjs.reporter)
1.  [function <span class="apidocSignatureSpan">gulp-w3cjs.</span>setW3cCheckUrl (newW3cCheckUrl)](#apidoc.element.gulp-w3cjs.setW3cCheckUrl)



# <a name="apidoc.module.gulp-w3cjs"></a>[module gulp-w3cjs](#apidoc.module.gulp-w3cjs)

#### <a name="apidoc.element.gulp-w3cjs.reporter"></a>[function <span class="apidocSignatureSpan">gulp-w3cjs.</span>reporter ()](#apidoc.element.gulp-w3cjs.reporter)
- description and source-code
```javascript
function reporter() {
	return through.obj(function(file, enc, cb) {
        cb(null, file);
        if (file.w3cjs && !file.w3cjs.success) {
            throw new gutil.PluginError('gulp-w3cjs', 'HTML validation error(s) found');
        }
    });
}
```
- example usage
```shell
...

'''javascript
var w3cjs = require('gulp-w3cjs');

gulp.task('w3cjs', function () {
	gulp.src('src/*.html')
		.pipe(w3cjs())
		.pipe(w3cjs.reporter());
});
'''

### Custom Reporting

The results are also added onto each file object under 'w3cjs', containing 'success' (Boolean) and 'messages' (Array).
...
```

#### <a name="apidoc.element.gulp-w3cjs.setW3cCheckUrl"></a>[function <span class="apidocSignatureSpan">gulp-w3cjs.</span>setW3cCheckUrl (newW3cCheckUrl)](#apidoc.element.gulp-w3cjs.setW3cCheckUrl)
- description and source-code
```javascript
function setW3cCheckUrl(newW3cCheckUrl) {
	w3cCheckUrl = newW3cCheckUrl;
}
```
- example usage
```shell
...
## API

### w3cjs(options)

#### options.url

URL to the w3c validator. Use if you want to use a local validator. This is the
same thing as 'w3cjs.setW3cCheckUrl()'.

#### options.proxy

Http address of the proxy server if you are running behind a firewall, e.g.  'http://proxy:8080'

_'options.doctype' and 'options.charset' were dropped in 1.0.0. Use 0.3.0 if you need them._
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
