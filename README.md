The project provides various tools for integrating and interacting with Swagger.  This project is in its infancy but
what is within the repository should be fully tested and reusable.  Please visit the [issue tracker][project-issues] to
see what issues we are aware of and what features/enhancements we are working on.  Otherwise, feel free to review the
[Release Notes][release-notes] to see what is new and improved.

## Project Badges

[![Join the chat at https://gitter.im/apigee-127/swagger-tools](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/apigee-127/swagger-tools?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

* Dependencies: [![Dependencies](https://david-dm.org/apigee-127/swagger-tools.svg)](https://david-dm.org/apigee-127/swagger-tools)
* Developer dependencies: [![Dev Dependencies](https://david-dm.org/apigee-127/swagger-tools/dev-status.svg)](https://david-dm.org/apigee-127/swagger-tools#info=devDependencies&view=table)
* Downloads: [![NPM Downloads Per Month](http://img.shields.io/npm/dm/swagger-tools.svg?style=flat)](https://www.npmjs.org/package/swagger-tools)
* License: [![License](http://img.shields.io/npm/l/swagger-tools.svg?style=flat)](https://github.com/apigee-127/swagger-tools/blob/master/LICENSE)
* Bower Version [![NPM Version](https://img.shields.io/bower/v/swagger-tools.svg?style=flat)](http://bower.io/search/?q=swagger-tools)
* NPM Version: [![NPM Version](http://img.shields.io/npm/v/swagger-tools.svg?style=flat)](https://www.npmjs.org/package/swagger-tools)

## Supported Swagger Versions

* [1.2][swagger-docs-v1_2]
* [2.0][swagger-docs-v2_0]

## Features

* Simple CLI
    * Validate Swagger document(s)
    * Convert Swagger 1.2 documents to Swagger 2.0
* Schema validation: For the file(s) supported by the Swagger specification, ensure they pass structural validation
based on the [JSON Schema][json-schema] associated with that version of the specification _(Browser and Node)_
* Semantic validation: Validates Swagger files above and beyond the structure of the file _(Browser and Node)_
* Connect middleware for adding pertinent Swagger information to your requests _(Node only)_
* Connect middleware for wiring up security handlers for requests based on Swagger documentation _(Node only)_
* Connect middleware for wiring request handlers to requests based on Swagger documentation _(Node only)_
* Connect middleware for serving your Swagger documents and [Swagger UI][swagger-ui] _(Node only)_
* Connect middleware for using Swagger resource documents for pre-route validation _(Node only)_
    * Validate the request/response Content-Type based on the operation's `consumes/produces` value(s)
    * Validate the request parameter types
    * Validate the request parameter values
    * Validate the response values

## Installation

Swagger Tools is available for both Node.js and the browser.  Installation instructions for each environment are below.

### Browser

Installation for browser applications can be done via [Bower][bower] or by downloading a standalone binary.

#### Using Bower

```
bower install swagger-tools --save
```

#### Standalone Binaries

The standalone binaries come in two flavors:

* [swagger-tools-standalone.js](https://raw.github.com/apigee-127/swagger-tools/master/browser/swagger-tools-standalone.js): _2,280kb_, full source _(including all dependencies)_ and source maps
* [swagger-tools-standalone-min.js](https://raw.github.com/apigee-127/swagger-tools/master/browser/swagger-tools-standalone-min.js): _316kb_, minified, compressed
and no sourcemap

### Node.js

Installation for Node.js applications can be done via [NPM][npm].

```
npm install swagger-tools --save
```

If you want to use the `swagger-tools` executable for validating Swagger documents, you can install swagger-tools
globally using the following:

```
npm install -g swagger-tools
```

## Documentation

swagger-tools is heavily documented so head on over to the project  [documentation][documentation] or jump straight to
the [Quick Start][quick-start].

## Contributing

This project uses [Gulp][gulp] for building so `npm install -g gulp` once you clone this project.  Running `gulp` in the
project root will lint check the source code and run the unit tests.

[bower]: http://bower.io/
[documentation]: https://github.com/apigee-127/swagger-tools/blob/master/docs/README.md
[gulp]: http://gulpjs.com/
[json-schema]: http://json-schema.org/
[npm]: https://www.npmjs.org/
[project-issues]: https://github.com/apigee/swagger-tools/issues
[quick-start]: https://github.com/apigee-127/swagger-tools/blob/master/docs/QuickStart.md
[release-notes]: https://github.com/apigee-127/swagger-tools/blob/master/RELEASE_NOTES.md
[swagger]: http://swagger.io/
[swagger-docs-v1_2]: https://github.com/swagger-api/swagger-spec/blob/master/versions/1.2.md
[swagger-docs-v2_0]: https://github.com/swagger-api/swagger-spec/blob/master/versions/2.0.md
[swagger-ui]: https://github.com/swagger-api/swagger-ui

## Legwork Fork
Changes to our forked version of this repo should be saved as `patch` files into the `./patches` folder so we have a concise history of the changes we've made to the repo. A `patch` file has the added benefit over a `diff` file because it also transfers the authorship info and the commit message.

### Creating the `patch` file
- Code your changes and make your commit(s).
- From a terminal, run the following command, replacing `<n>` with the number of topmost commits from the current branch to include:
   ```
   git format-patch -o ./patches -<n>
   ```

### Updating latest `master` and applying the `./patches` folder
- Update to the latest `master` (checkout `master` and `git pull`).
- Checkout or create a new branch.
- Apply all of the patches contained in the `./patches` folder:
   ```
   git am ./patches/*
   ```
- `git push` your branch.