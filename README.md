<img src="https://raw.githubusercontent.com/dreipol/scss-mq/main/logo.png" width="50%"/>

# scss-mq

Dreipol scss media queries helper

[![Build Status][travis-image]][travis-url]
[![NPM version][npm-version-image]][npm-url]
[![NPM downloads][npm-downloads-image]][npm-url]
[![MIT License][license-image]][license-url]


# Documentation

- [API](https://www.dreipol.dev/scss-mq/)
- [Demo](https://www.dreipol.dev/scss-mq/demo)

# Usage 

## Installation

```bash
npm i @dreipol/scss-mq -S
```

## Import

You can import the `mq` mixin in your sass files simply using the `@use` rule for example:

```scss
@use 'node_modules/@dreipol/scss-mq' as *;

a {
    @include mq('xs') {
        color: red;
    }
} 
```

Notice that you can override the internal module variables using the `with` rule for example:

```scss
@use 'node_modules/@dreipol/scss-mq' as * with (
    $breakpoints: (xs: 600px, sm: 767px, md: 991px, lg: 1279px, xl: 1599px)
);

a {
    @include mq('xs') {
        color: red;
    }
} 
```

**IMPORTANT** You should override the internal `scss-mq` variables **only once** and at beginning of your `main.scss` file.`For example

In `main.scss`

```scss
@use 'node_modules/@dreipol/scss-mq' as * with (
    $breakpoints: (xs: 600px, sm: 767px, md: 991px, lg: 1279px, xl: 1599px)
);
// Grid
@use 'path/to/grid';

// components
@use 'path/to/a/component-b';
@use 'path/to/a/component-b';
```

In `grid.scss`

```scss
// you don't need to override again the breakpoints here!
@use 'node_modules/@dreipol/scss-mq' as *;

.grid {
    @include mq('xs') {
        width: 100%;
    }
}
```

[travis-image]:https://img.shields.io/travis/dreipol/scss-mq.svg?style=flat-square
[travis-url]:https://travis-ci.org/dreipol/scss-mq

[license-image]:http://img.shields.io/badge/license-MIT-000000.svg?style=flat-square
[license-url]:LICENSE

[npm-version-image]:http://img.shields.io/npm/v/@dreipol/scss-mq.svg?style=flat-square
[npm-downloads-image]:http://img.shields.io/npm/dm/@dreipol/scss-mq.svg?style=flat-square
[npm-url]:https://npmjs.org/package/@dreipol/scss-mq
