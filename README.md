# ki.js

ki.js is a super-tiny jQuery-like JavaScript Library (554 bytes | 348 gzipped)

## What can i do with ki.js?

With ki.js you can do the basic stuff jQuery can, for example:

### DOM Ready?

```javascript
$(function () {
  // this will be executed when the dom is ready!
  alert('Hey the DOM is ready ;)');
});
```
**This was just ki.js, no jQuery**

### CSS Selectors
Use any CSS selector that exists to get elements from the DOM.


### Events
Yes, events with the known `.on()` and `.off()` methods

```html
<button>ki.js</button>
```
```javascript
$(function () {
  // ok now that the dom is ready i would like to add some events
  var alertMyName = function () {
    alert('My name is ' + this.textContent); // will allert 'ki.js'
  };
  
  $('button').on('click', alertMyName);
  // to turn it off just use .off()
  //$('button').off('click', alertMyName);
});
```
You can add any JavaScript event even touch events for mobile, under the hood ki.js uses addEventListener, so feel free to use any valid ECMAScript 5 event.

### each()
The `each()` is also included in the core of ki.js for easy iterating a DOM collection.

```javascript
$(function () {
  // get all p tags
  $('p').each(function (elem, i) {
    // change color to red
    elem.style.color = 'red';
    // append the index to the text
    elem.textContent += i;
  });
});
```

### Keep the chain!
All methods of ki.js are chainable, just like jQuery.

## Plugins?
Yeah, you could write plugins for ki.js if you want, fork the project for making them, keep them super super xxs and I promise to merge them into the official repo.

### How to make plugins?
Just add your methods to the prototype of ki.js and you're done.
For example, let's add a `text()` method for setting or getting the text of the elements, in the tiniest way I can think of:

```javascript
// minified is 106 bytes
$.prototype.text = function (a) {
  return a === []._ ? this[0].textContent : this.each(function (b) {
    b.textContent = a
  })
};
```

Now use the plugin just like the other methods:
```javascript
$(function () {
  // <p>hello</p>
  
  // get the text from the p tag
  console.log($('p').text()); // hello
  
  // set another text
  $('p').text('bye'); // bye
});
```
<hr>
<strong>Create your own plugin and let's make the tiniest JavaScript Library ever!
Remember to write byte-saving code, see this [useful resource for JavaScript byte-saving techniques](https://github.com/jed/140bytes/wiki/Byte-saving-techniques) written by 140byt.es community</strong>
<hr>

## Where can i use ki.js?

In every cool and modern browser.

## The Code
The code of ki.js was written for byte-saving, so I don't recommend you using this type of programming for a real application or website.
It was done for fun, and the funniest part is that it actually works :)

The code is a bit commented so you can learn from it.

## License
See [LICENSE.txt](https://raw.github.com/dciccale/ki.js/master/LICENSE.txt)
