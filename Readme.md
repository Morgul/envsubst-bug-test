# Bug Reproduction for `tuplo/envsubst` #5

Simply:
  1. Run `npm build`
  2. Run `npm start`

You should see an error message like the following:

```
~/d/envsubst-bug-test > npm start

> envsubst-bug-test@1.0.0 start
> node ./dist/index.js

internal/modules/cjs/loader.js:1080
      throw new ERR_REQUIRE_ESM(filename, parentPath, packageJsonPath);
      ^

Error [ERR_REQUIRE_ESM]: Must use import to load ES Module: /home/ccase/devel/envsubst-bug-test/node_modules/@tuplo/envsubst/cjs/index.js
require() of ES modules is not supported.
require() of /home/ccase/devel/envsubst-bug-test/node_modules/@tuplo/envsubst/cjs/index.js from /home/ccase/devel/envsubst-bug-test/dist/index.js is an ES module file as it is a .js file whose nearest parent package.json contains "type": "module" which defines all .js files in that package scope as ES modules.
Instead rename /home/ccase/devel/envsubst-bug-test/node_modules/@tuplo/envsubst/cjs/index.js to end in .cjs, change the requiring code to use import(), or remove "type": "module" from /home/ccase/devel/envsubst-bug-test/node_modules/@tuplo/envsubst/package.json.

    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1080:13)
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14)
    at Module.require (internal/modules/cjs/loader.js:952:19)
    at require (internal/modules/cjs/helpers.js:88:18)
    at Object.<anonymous> (/home/ccase/devel/envsubst-bug-test/dist/index.js:9:36)
    at Module._compile (internal/modules/cjs/loader.js:1063:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1092:10)
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14) {
  code: 'ERR_REQUIRE_ESM'
}
```