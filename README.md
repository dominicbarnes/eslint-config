# eslint-config

> ESLint configuration for my personal projects.

## Usage

Since I have a lot of varying JS projects, I've got several "sub-modules" that are suited to
various environments. Each project will likely import several of these modules, since ESLint
allows extending with multiple sources:

 - [@dominicbarnes/browser](https://github.com/dominicbarnes/eslint-config-browser)
   is used for browser projects.
 - [@dominicbarnes/node](https://github.com/dominicbarnes/eslint-config-node)
   is used for node projects.
 - [@dominicbarnes/mako](https://github.com/dominicbarnes/eslint-config-mako)
   is used for browser projects built with mako.
 - [@dominicbarnes/deku](https://github.com/dominicbarnes/eslint-config-deku)
   is used for projects that use deku. (and consequently, a lot of ES6)
 - [@dominicbarnes/test](https://github.com/dominicbarnes/eslint-config-test)
   is used for my project tests, all currently requiring mocha.

For apps, where there is likely a mixture of server and browser code, the root `.eslintrc` will
likely extend the core configuration (ie: `@dominicbarnes`) directly. This allows specific
subdirectories to be given the configuration sub-module more suited to them.

For example, in a project that uses node.js for the server, with deku on the client:

 * .eslintrc: `{ "extends": "@dominicbarnes" }`
 * client/.eslintrc: `{ "extends": [ "@dominicbarnes/mako", "@dominicbarnes/browser", "@dominicbarnes/deku" }`
 * server/.eslintrc: `{ "extends": "@dominicbarnes/node" }`
