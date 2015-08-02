
# eslint-config

> ESLint configuration for my personal projects.

## Usage

Since I have a lot of varying JS projects, I've got several "sub-modules" that are
suited to various environments:

 - [@dominicbarnes/browser](https://github.com/dominicbarnes/eslint-config-browser)
   is used for browser projects.
 - [@dominicbarnes/node](https://github.com/dominicbarnes/eslint-config-node)
   is used for node/iojs projects.
 - [@dominicbarnes/deku](https://github.com/dominicbarnes/eslint-config-deku)
   is used for projects that use deku. (and consequently, a lot of ES6)
 - [@dominicbarnes/test](https://github.com/dominicbarnes/eslint-config-test)
   is used for my project tests, all currently requiring mocha.

For apps, where there is likely a mixture of server and browser code, the root `.eslintrc`
will likely extend the core configuration (ie: `@dominicbarnes`) directly. This allows
specific subdirectories to be given the configuration sub-module more suited to them.

For example:

 * .eslintrc: `{ "extends": "@dominicbarnes" }`
 * client/.eslintrc: `{ "extends": "@dominicbarnes/browser" }`
 * server/.eslintrc: `{ "extends": "@dominicbarnes/server" }`

For libs, where the project will be likely be dedicated to either the server or browser,
then a sub-module will likely be extended directly.
