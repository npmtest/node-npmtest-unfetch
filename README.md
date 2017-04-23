# npmtest-unfetch

#### basic test coverage for  [unfetch (v2.1.2)](https://github.com/developit/unfetch)  [![npm package](https://img.shields.io/npm/v/npmtest-unfetch.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-unfetch) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-unfetch.svg)](https://travis-ci.org/npmtest/node-npmtest-unfetch)

#### Bare minimum fetch polyfill in 500 bytes

[![NPM](https://nodei.co/npm/unfetch.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/unfetch)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-unfetch/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-unfetch/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-unfetch/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-unfetch/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-unfetch/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-unfetch/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-unfetch/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-unfetch/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-unfetch/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-unfetch/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-unfetch/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-unfetch/build/test-report.html](https://npmtest.github.io/node-npmtest-unfetch/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-unfetch/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-unfetch/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-unfetch/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-unfetch/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-unfetch/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-unfetch/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-unfetch/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-unfetch/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "authors": [
        "Jason Miller <jason@developit.ca>"
    ],
    "bugs": {
        "url": "https://github.com/developit/unfetch/issues"
    },
    "dependencies": {},
    "description": "Bare minimum fetch polyfill in 500 bytes",
    "devDependencies": {
        "babel-core": "^6.9.1",
        "babel-eslint": "^7.1.1",
        "babel-preset-es2015": "^6.9.0",
        "babel-preset-stage-0": "^6.5.0",
        "babel-register": "^6.9.0",
        "chai": "^3.5.0",
        "cross-env": "^3.1.4",
        "eslint": "^3.13.1",
        "gzip-size-cli": "^1.0.0",
        "mkdirp": "^0.5.1",
        "mocha": "^3.2.0",
        "npm-run-all": "^2.1.1",
        "rimraf": "^2.5.2",
        "rollup": "^0.41.4",
        "rollup-plugin-buble": "^0.15.0",
        "rollup-plugin-post-replace": "^1.0.0",
        "sinon": "^1.17.4",
        "sinon-chai": "^2.8.0",
        "strip-json-comments-cli": "^1.0.1",
        "uglify-js": "^2.6.2"
    },
    "directories": {},
    "dist": {
        "shasum": "684fee4d8acdb135bdb26c0364c642fc326ca95b",
        "tarball": "https://registry.npmjs.org/unfetch/-/unfetch-2.1.2.tgz"
    },
    "eslintConfig": {
        "parser": "babel-eslint",
        "extends": "eslint:recommended",
        "env": {
            "browser": true,
            "mocha": true,
            "node": true,
            "es6": true
        },
        "globals": {
            "expect": true
        }
    },
    "files": [
        "src",
        "dist",
        "polyfill.js"
    ],
    "gitHead": "edc961b06b4a971381e6261201485907e4a0d6d1",
    "homepage": "https://github.com/developit/unfetch",
    "jsnext:main": "dist/unfetch.es.js",
    "keywords": [
        "fetch",
        "polyfill",
        "xhr",
        "ajax"
    ],
    "license": "MIT",
    "main": "dist/unfetch.js",
    "maintainers": [
        {
            "name": "developit"
        }
    ],
    "module": "dist/unfetch.es.js",
    "name": "unfetch",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/developit/unfetch.git"
    },
    "scripts": {
        "build": "npm-run-all --silent clean -p rollup:* -p minify:* -s size",
        "clean": "rimraf dist && mkdirp dist",
        "minify:cjs": "uglifyjs $npm_package_main -cm toplevel -o $npm_package_main -p relative --in-source-map ${npm_package_main}.map --source-map ${npm_package_main}.map",
        "minify:umd": "uglifyjs $npm_package_umd_main -cm -o $npm_package_umd_main -p relative --in-source-map ${npm_package_umd_main}.map --source-map ${npm_package_umd_main}.map",
        "prepublish": "npm run -s build",
        "release": "npm run build -s && git commit -am $npm_package_version && git tag $npm_package_version && git push && git push --tags && npm publish",
        "rollup:cjs": "cross-env FORMAT=cjs rollup -c rollup.config.js -f cjs -n $npm_package_name -o $npm_package_main",
        "rollup:esm": "rollup -c rollup.config.js -f es -n $npm_package_name -o $npm_package_module",
        "rollup:umd": "cross-env FORMAT=umd rollup -c rollup.config.js -f umd -n $npm_package_name -o $npm_package_umd_main",
        "size": "echo \"Gzipped Size: $(strip-json-comments --no-whitespace $npm_package_main | gzip-size)\"",
        "test": "eslint src test && mocha --compilers js:babel-register test/**/*.js"
    },
    "umd:main": "dist/unfetch.umd.js",
    "version": "2.1.2",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
