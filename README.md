![](https://dl.dropboxusercontent.com/u/1803181/essential-react-logo.png)

[![Travis branch](https://img.shields.io/travis/pheuter/essential-react.svg?style=flat-square)](https://travis-ci.org/pheuter/essential-react)
[![Coveralls](https://img.shields.io/coveralls/pheuter/essential-react.svg?style=flat-square)](https://coveralls.io/r/pheuter/essential-react)
[![npm](https://img.shields.io/npm/v/essential-react.svg?style=flat-square)](https://www.npmjs.com/package/essential-react)
[![David](https://img.shields.io/david/pheuter/essential-react.svg?style=flat-square)](https://david-dm.org/pheuter/essential-react)

A minimal skeleton for building testable React apps using ES6.

- [Design Goals](#design-goals)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
  - [Dev](#dev)
- [Project structure](#project-structure)
- [Commands](#commands)
  - [server](#server)
  - [build](#build)
  - [test](#test)
  - [coveralls](#coveralls)
  - [clean](#clean)
- [TODO](#todo)

## Design Goals

- As few tools as possible (no yeoman, gulp, bower, etc...)
- ES6 with polyfills for current browsers
- Testability: ease of writing unit tests and generating code coverage
- Minimize templates, compose DOM alongside components via JSX
- Session-driven routing using [react-router](https://github.com/rackt/react-router) with async data fetching

## Getting Started

```sh
$ npm install
```

Start the local dev server:

```sh
$ npm run server
```

Navigate to **http://localhost:8080/** to view the app.

## Dependencies

- [react v0.12](http://facebook.github.io/react/)
- [react-router v0.12](https://github.com/rackt/react-router)

### Dev

- [webpack](http://webpack.github.io/)
- [react hot loader](https://github.com/gaearon/react-hot-loader)
- [karma](http://karma-runner.github.io/0.12/index.html)
- [babel](http://babeljs.io/)

Check out [package.json](package.json) for the complete list.

## Project structure

![](https://www.dropbox.com/s/j936nd4j57u45cb/Screenshot%202015-03-08%2016.56.05.png?dl=1)

Components are grouped into 2 main categories:

- **common** - contains various classes and components that are shared between pages and views
- **pages** - contains components grouped by the page / view / feature they belong to.

A case can be made to move **routers** into **common**, but I felt it made sense to keep them in their own section.

## Commands

A core philosophy of this skeleton app is to keep the tooling to a minimum. For this reason, you can find all the commands in the `scripts` section of [package.json](package.json).

### server

```sh
$ npm run server
```

**Input:** `src/main.jsx`

This leverages [React Hot Loader](https://github.com/gaearon/react-hot-loader) to automatically start a local dev server and refresh file changes on the fly without reloading the page.

It also automatically includes source maps, allowing you to browse code and set breakpoints on the original ES6 code:

![](https://www.dropbox.com/s/zgb3psadwcawjc8/Screenshot%202015-03-08%2017.09.53.png?dl=1)

### build

```sh
$ npm run build
```

**Input:** `src/main.jsx`

**Output:** `build/app.js`

Build minified app for production using the [production](http://webpack.github.io/docs/cli.html#production-shortcut-p) shortcut.

### test

```sh
$ npm test
```

**Input:** `test/main.js`

**Output:** `coverage/`

Leverages [Karma](http://karma-runner.github.io/0.12/index.html) to run through the test suite using [PhantomJS](http://phantomjs.org/) and generate code coverage reports.

### coveralls

```sh
$ npm run coveralls
```

**Input:** `coverage/lcov.info`

Sends the code coverage report generated by [Istanbul](https://github.com/gotwarlost/istanbul) to [Coveralls](http://coveralls.io/).

### clean

```sh
$ npm run clean
```

**Input:** `build/app.js`

Removes the compiled app file from build.