[![NPM version](http://img.shields.io/npm/v/generator-polymer.svg?style=flat)](http://npmjs.org/generator-polymer)
[![NPM downloads](http://img.shields.io/npm/dm/generator-polymer.svg?style=flat)](http://npmjs.org/generator-polymer)
[![Build Status](http://img.shields.io/travis/yeoman/generator-polymer/master.svg?style=flat)](https://travis-ci.org/yeoman/generator-polymer)
[![Dependency Status](http://img.shields.io/david/yeoman/generator-polymer.svg?style=flat)](https://david-dm.org/yeoman/generator-polymer)

## Yeoman generator for Polymer projects

<img src="http://i.imgur.com/dsFChIk.png"/>

## Introduction

[Polymer](http://www.polymer-project.org/) is a library of polyfills and sugar which enable the use of Web Components in modern browsers. The project allows developers to build apps using the platform of tomorrow and inform the W3C of places where in-flight specifications can be further improved.

`generator-polymer` provides Polymer scaffolding using [Yeoman](http://yeoman.io) (a scaffolding tool for the web), letting you easily create and customize Polymer (custom) elements via the command-line and import them using HTML Imports. This saves you time writing boilerplate code so you can start writing up the logic to your components straight away.

## Features

* A Polymer app scaffold built with HTML5 Boilerplate
* Sub-generator to create Polymer elements for your app
* Boilerplate to create reusable Polymer elements
* Quick deploy to GitHub pages
* All the goodness of `seed-element` (docs & landing page for your element)
* Support for SASS/SCSS and Autoprefixer
* PageSpeed Insights for performance tuning
* Mocha test stubs

## Installation

Install the generator
`npm install -g generator-polymer`

Make a new directory and cd into it
`mkdir -p my-project && cd $_`

Scaffold a new Polymer project:
`yo polymer`

## Generators

Available generators:

- [polymer (aka polymer:app)](#app)
- [polymer:element](#element-alias-el)
- [polymer:seed](#seed)
- [polymer:gh](#gh)

**Note: Generators are to be run from the root of your app**

### App
Sets up a new Polymer app, generating all the boilerplate you need to get started.

Example:
```bash
yo polymer
```

### Element (alias: El)
Generates a polymer element in `app/elements` and appends an import to `app/elements/elements.html`.

Example:
```bash
yo polymer:element my-element

# or use the alias

yo polymer:el my-element
```

**Note: You must pass in an element name, and the name must contain a dash "-"**

One can also include element dependencies to be imported. For instance, if you're creating a `fancy-menu` element which needs to import `core-menu` and `core-icon-button` as dependencies, you can generate the file like so:

```bash
yo polymer:el fancy-menu core-menu core-icon-button
```

### Seed
Generates a reusable polymer element based on the [seed-element workflow](http://www.polymer-project.org/docs/start/reusableelements.html). **This should only be used if you're creating a standalone element repo that you intend to share with others via bower.** If you're just building a Polymer app, stick to the [Element](#element-alias-el) generator.

The seed-element generator will construct a new element _and_ its directory for
you. Be aware: all bower dependencies will be installed as _siblings_ of the
newly generated element. Make sure that you generate the seed element within a
directory that is intended to contain multiple components!

Example:
```bash
mkdir -p components && cd $_
yo polymer:seed x-foo
```

### Gh
Generates a Github pages branch for your [seed-element](#seed).

Example:
```bash
cd components/x-foo
yo polymer:gh
```

## Gotchas

### Autoprefixer and style elements

The Autoprefixer task will not work with `style` elements mixed into HTML files (it breaks). Meaning, if you drop a style tag inside of your Polymer element, it will not be processed by Autoprefixer. **Only external CSS files can/will be processed by Autoprefixer**.

## Contribute

See the [contributing docs](https://github.com/yeoman/yeoman/blob/master/contributing.md)

When submitting an issue, please follow the [guidelines](https://github.com/yeoman/yeoman/blob/master/contributing.md#issue-submission). Especially important is to make sure Yeoman is up-to-date, and providing the command or commands that cause the issue.

## License

[BSD license](http://opensource.org/licenses/bsd-license.php)
