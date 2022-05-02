---
aliases: 
created: 2022-03-11, 9:54:28 am (Friday, March 11th)
updated: 2022-03-11, 10:00:11 am (Friday, March 11th)
---
## Where did I see this?

Trying to figure out why a [[Tech/Concourse|Concourse CI]] pipeline was not running.

I kept seeing the error:

```
Running linter


> <repo> lint /path/to/temp/build

> eslint . --ext .ts



Oops! Something went wrong! :(


ESLint: 8.9.0


TypeError: Module.createRequire is not a function

    at Object.<anonymous> (/path/to/temp/build/node_modules/@eslint/eslintrc/dist/eslintrc.cjs:2383:26)

    at Module._compile (/path/to/temp/build/node_modules/v8-compile-cache/v8-compile-cache.js:192:30)

    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)

    at Module.load (internal/modules/cjs/loader.js:653:32)

    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)

    at Function.Module._load (internal/modules/cjs/loader.js:585:3)

    at Module.require (internal/modules/cjs/loader.js:692:17)

    at require (/path/to/temp/build/node_modules/v8-compile-cache/v8-compile-cache.js:159:20)

    at Object.<anonymous> (/path/to/temp/build/node_modules/eslint/lib/cli-engine/cli-engine.js:33:5)

    at Module._compile (/path/to/temp/build/node_modules/v8-compile-cache/v8-compile-cache.js:192:30)

npm ERR! code ELIFECYCLE

npm ERR! errno 2

npm ERR! <repo> lint: `eslint . --ext .ts`

npm ERR! Exit status 2

npm ERR! 

npm ERR! Failed at the <repo> lint script.

npm ERR! This is probably not a problem with npm. There is likely additional logging output above.


npm ERR! A complete log of this run can be found in:

npm ERR!     /root/.npm/_logs/<timestamp>-debug.log
```

This line specifically confused me:

`TypeError: Module.createRequire is not a function`

After googling, the problem turned out to be not having the right version of Node for ESLint

Kudos: https://stackoverflow.com/questions/70390777/error-in-module-createrequire-is-not-a-function