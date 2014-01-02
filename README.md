# jQuery Evergreen

Small & fast DOM and event library for modern browsers.
Having the same familiar API as jQuery (but without the extra "weight" of modules like `$.ajax`, `$.animate`, and `$.Deferred`), it works great stand-alone or paired up with e.g. Backbone.
The full version is only 7KB minified (2KB gzip), but it's easy to create a custom build to exclude parts you don't need.

The [annotated](http://webpro.github.io/jquery-evergreen/main.html) source is written in the ES6 Modules format, and transpiled to an AMD and a CommonJS version using the [ES6 Module Transpiler](http://square.github.io/es6-module-transpiler/). And last but also least, the CommonJS version is "browserified".

## Quickstart

### AMD

    # Install
	bower install jquery-evergreen

	# Configure
	paths: {
		'jquery-evergreen': 'lib/jquery-evergreen/dist/jquery-evergreen.amd'
	}

	# Use
	define(['jquery-evergreen'], function($) {
		$('.earth').addClass('evergreen').on('sunrise', '.people', awake);
	});

### Browser Global

    # Install
	bower/npm install jquery-evergreen

	# Configure
	<script src="dist/jquery-evergreen.js"></script>

	# Use
	$('.planet').addClass('evergreen').on('sunrise', '.grass', grow);

## API

### [Attr](http://webpro.github.io/jquery-evergreen/je/attr.html)

	attr

### [Class](http://webpro.github.io/jquery-evergreen/je/class.html)

	addClass
	removeClass
	toggleClass
	hasClass

### [DOM](http://webpro.github.io/jquery-evergreen/je/dom.html)

	append
	before
	after

### [Event](http://webpro.github.io/jquery-evergreen/je/event.html)

	on
	off
	delegate
	undelegate
	trigger

### [HTML](http://webpro.github.io/jquery-evergreen/je/html.html)

	html

### [Mode](http://webpro.github.io/jquery-evergreen/je/mode.html)

	isNative
	native

### [NoConflict](http://webpro.github.io/jquery-evergreen/je/noconflict.html)

	noConflict

### [Selector](http://webpro.github.io/jquery-evergreen/je/selector.html)

	$
	find

## But it doesn't even have ...!

As mentioned in the introduction, jQuery Evergreen doesn't have methods for your Ajax, Animation and Deferred needs. Please find your own libraries to fill in the gaps as needed. Here are just some examples:

* Ajax: [microjs#ajax](http://microjs.com/#ajax), [rest.js](https://github.com/cujojs/rest)
* Animation: [microjs#animation](http://microjs.com/#animation), [Move.js](http://visionmedia.github.io/move.js/), [Animate.css](https://daneden.me/animate/)
* Deferred (aka promises): [when.js](https://github.com/cujojs/when), [RSVP.js](https://github.com/tildeio/rsvp.js)

However, feel free to [open an issue](https://github.com/webpro/jquery-evergreen/issues) if you feel an important method is missing.

## Browser Support

Latest versions of Chrome, Firefox, Safari, Opera, Chrome Mobile iOS, and Mobile Safari. IE10 and IE11. IE9 only needs a polyfill for `classList` to make these tests pass.

## Performance

Some tests comparing the performance of jQuery, Zepto, and jQuery Evergreen:

* [Selector (simple)](http://jsperf.com/jquery-zepto-evergreen-simple-selector) - `$('.foo')`
* [Selector (complex)](http://jsperf.com/jquery-zepto-evergreen-complex-selector) - `$('.a .b > .c + .c article > [data-foo]').find('ul > li:first-child')`
* [Class](http://jsperf.com/jquery-zepto-evergreen-class) - `addClass`, `removeClass`, `toggleClass`
* [DOM manipulation](http://jsperf.com/jquery-zepto-evergreen-dom-manipulation) - `append`, `before`, `after`, `html`
* [Attr](http://jsperf.com/jquery-zepto-evergreen-attr) - `attr`

## Native Mode

You can [opt-in](http://webpro.github.io/jquery-evergreen/je/mode.html) to work directly with `Node` and live `NodeList` objects, as opposed to the default, wrapped `$` object.

## Custom Build

	npm install jquery-evergreen
	cd jquery-evergreen
	npm install
	grunt --exclude=attr,mode,html

And find the AMD, CommonJS and browserified versions in the `/dist` folder.

## Test

Run the [test suite](http://webpro.github.io/jquery-evergreen/test/). You can also get it from Github or npm, and find the `/test` folder.

## Credits

Many thanks to these sources of inspiration:

* [remy/min.js](https://github.com/remy/min.js)
* [Knockout](https://github.com/knockout/knockout/blob/master/src/utils.js)
* [inkling/Backbone.Native](https://github.com/inkling/backbone.native/blob/master/backbone.native.js)
* [madrobby/zepto](https://github.com/madrobby/zepto/)

## License

[MIT licensed](http://webpro.mit-license.org)

![Analytics](https://ga-beacon.appspot.com/UA-17415234-3/jquery-evergreen/readme?pixel)
