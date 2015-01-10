# vue-i18n

[![Build Status](https://travis-ci.org/kazupon/vue-i18n.svg?branch=master)](https://travis-ci.org/kazupon/vue-i18n)
[![Coverage Status](https://img.shields.io/coveralls/kazupon/vue-i18n.svg)](https://coveralls.io/r/kazupon/vue-i18n?branch=master)
[![NPM version](https://badge.fury.io/js/vue-i18n.svg)](http://badge.fury.io/js/vue-i18n)
[![Dependency Status](https://david-dm.org/kazupon/vue-i18n.svg)](https://david-dm.org/kazupon/vue-i18n) 
[![Sauce Test Status](https://saucelabs.com/buildstatus/vue-i18n)](https://saucelabs.com/u/vue-i18n)


Internationalization plugin of Vue.js


# Requirments
- works with Vue.js ^`0.10.4`


# Instllation

## component

```shell
$ component install kazupon/vue-i18n
```

## bower

```shell
$ bower install vue-i18n
```

## browserify

```shell
$ npm install vue-i18n
```


# Usage

## v-t directive

```js
var Vue = require('vue')
var i18n = require('vue-i18n')

// ready translated locales
var locales = {
  en: {
    message: {
      hello: 'the world'
    }
  },
  ja: {
    message: {
      hello: 'ザ・ワールド'
    }
  }
}

// set plugin
Vue.use(i18n, {
  lang: 'ja',
  locales: locales // NOTE: 'resources' is deprecated
})

// create instance
new Vue({
  el: '#test-i18n'
})
```

Template the following:

```html
<div id="test-i18n" class="message">
  <p v-t="message.hello"></p>
</div>
```

Output the following:

```html
<div id="test-i18n" class="message">
  <p>ザ・ワールド</p>
</div>
```

## Vue.t function

```js
var Vue = require('vue')
var i18n = require('vue-i18n')

// ready translated locales
var locales = {
  en: {
    message: {
      hello: 'the world'
    }
  },
  ja: {
    message: {
      hello: 'ザ・ワールド'
    }
  }
}

// set plugin
Vue.use(i18n, {
  lang: 'en',
  locales: locales
})

console.log(Vue.t('message.hello')) // output the 'the wolrd'
```

## $t method (for 0.11.4 later)

```html
<div id="message">
Message:<br>{{$t('message.hello')}}
</div>
```

```js
var Vue = require('vue')
var i18n = require('vue-i18n')

// ready translated locales
var locales = {
  en: {
    message: {
      hello: 'the world'
    }
  },
  ja: {
    message: {
      hello: 'ザ・ワールド'
    }
  }
}

// set plugin
Vue.use(i18n, {
  lang: 'en',
  locales: locales
})

new Vue().$mount('#message')
```

render the following:

```html
<div id="message">
Message:<br>the world
</div>
```

# Testing

```shell
$ make test
```


# TODO
See the `TODO.md`


# License

## MIT

See the `LICENSE`.