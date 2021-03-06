Number polyfill
================

This is a polyfill for implementing the HTML5 **&lt;input type="number"&gt;** element in browsers that do not currently support it.

Difference
================
What's the difference between this and [the original number polyfill](https://github.com/jonstipe/number-polyfill)?

Well, the original version uses relative positioning wich destroys layouts way to easy. 
This implementation changes that by doing an absolute positioning of the tickers instead.

Usage
===============

Using it is easy — simply include the **number-polyfill.js** file in the HEAD of the HTML page. Add a simple modernizr check like so
<pre>
	$(document).ready( function() {
		if (!Modernizr.inputtypes.number) {
			numberPolyfillInit();
		};
	});
</pre>
and you can then use &lt;input type="number"&gt; elements normally.

If Modernizr detects that the browser doesn't support &lt;input type="number"&gt;, the script will search for these elements and attach some Javascript to them to make them function as number-only input fields, and add increment/decrement buttons.

A default CSS file is provided. You may edit this file to style the buttons to make them look the way you want.

Dependencies
==============

This script requires [jQuery](http://jquery.com/) (tested with version 1.4.4 & 1.7.2) and [Modernizr](http://www.modernizr.com/).