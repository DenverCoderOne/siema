# Siemano - Lightweight and simple carousel with no dependencies

**This is a maintained fork of [Siema](https://github.com/pawelgrzybek/siema) by [Paweł Grzybek](https://github.com/pawelgrzybek).**

Full docs with examples: [https://denvercoderone.github.io/siemano/](https://denvercoderone.github.io/siemano/).

Siemano is a lightweight (only 3kb gzipped) carousel plugin with no dependencies and no styling. As Brad Frost once said, "do that shit yourself". It is 100% open source and [available on GitHub](https://github.com/DenverCoderOne/siemano). It is free to use on personal and commercial projects. Use it with your favorite module bundler or by manually injecting the script into your project.

## Installation

Setup is trivially easy. A little bit of markup...

```html
<div class="siema">
  <div>Hi, I'm slide 1</div>
  <div>Hi, I'm slide 2</div>
  <div>Hi, I'm slide 3</div>
  <div>Hi, I'm slide 4</div>
</div>
```

**Option 1:** If you are using a module bundler like Webpack or Browserify...

```
yarn add siemano
```

```js
import Siema from "siemano";
new Siema();
```

**Option 2:** Install from a CDN such as [jsDelivr](https://www.jsdelivr.com/package/npm/siemano)...

```html
<script src="https://cdn.jsdelivr.net/gh/DenverCoderOne/siemano@1.6.0/dist/siema.min.js" type="text/javascript"></script>
<script>
  new Siema();
</script>
```

**Option 3:** Manually inject the minified script into your website...

```html
<script src="siema.min.js" type="text/javascript"></script>
<script>
  new Siema();
</script>
```

## Options

Siemano comes with a few (optional) settings that you can change by passing an object as an argument. Default values are presented below.

```js
new Siema({
  selector: ".siema",
  duration: 200,
  easing: "ease-out",
  perPage: 1,
  startIndex: 0,
  draggable: true,
  multipleDrag: true,
  threshold: 20,
  loop: false,
  rtl: false,
  autoHeight: false,
  onInit: () => {},
  onChange: () => {},
  onResize: () => {},
});
```

**`selector`** (string or DOM element)  
The selector to use as a carousel. Siema will use all immediate children of this selector as slider items. It can be a query string [(example)](http://codepen.io/pawelgrzybek/pen/QvLjxY) or a DOM element [(example)](http://codepen.io/pawelgrzybek/pen/gWYaje).

**`duration`** (number)  
Slide transition duration in milliseconds [(example)](http://codepen.io/pawelgrzybek/pen/BRBoqO).

**`easing`** (string)  
Like a CSS `transition-timing-function`, it describes the acceleration curve [(example)](http://codepen.io/pawelgrzybek/pen/aWovrB).

**`perPage`** (number or object)  
The number of slides to be shown. It accepts a number [(example)](http://codepen.io/pawelgrzybek/pen/bWbVXz) or an object [(example)](http://codepen.io/pawelgrzybek/pen/dWbGyZ) for complex responsive layouts.

**`startIndex`** (number)  
Index (zero-based) of the starting slide [(example)](http://codepen.io/pawelgrzybek/pen/vmBLER).

**`draggable`** (boolean)  
Use dragging and touch swiping [(example)](http://codepen.io/pawelgrzybek/pen/mmbVVj).

**`multipleDrag`** (boolean)  
Allow dragging to move multiple slides.

**`threshold`** (number)  
Touch and mouse dragging threshold (in px) [(example)](http://codepen.io/pawelgrzybek/pen/gWYPrQ).

**`loop`** (boolean)  
Loop the slides around [(example)](http://codepen.io/pawelgrzybek/pen/zwOrKN).

**`rtl`** (boolean)  
Enables layout for languages written from right to left (like Hebrew or Arabic) [(example)](https://codepen.io/pawelgrzybek/pen/XZNEgd).

**`autoHeight`** (boolean)  
Enable automatically adjusting the height of the frame to match the currently active slides [(example)](https://codepen.io/eyl327/pen/abGzOrx).

**`onInit`** (function)  
Runs immediately after initialization [(example)](http://codepen.io/pawelgrzybek/pen/BRBjpE).

**`onChange`** (function)  
Runs after slide change [(example)](http://codepen.io/pawelgrzybek/pen/RVbrVe).

**`onResize`** (function)  
Runs on window resize after the frame is rebuilt [(example)](https://codepen.io/eyl327/pen/OJZPVRy).

## API

As mentioned above, Siema doesn't come with many options - just a few useful methods. Combine it with some very basic JavaScript and voila!

**`prev(howManySlides = 1, callback)`**  
Go to the previous item [(example)](http://codepen.io/pawelgrzybek/pen/JNPKVE). Optionally slide a few items backward by passing `howManySlides` (number) argument [(example)](http://codepen.io/pawelgrzybek/pen/wdwWZQ). Optional `callback` (function) available as a third argument [(example)](http://codepen.io/pawelgrzybek/pen/JNPKQW).

**`next(howManySlides = 1, callback)`**  
Go to the next item [(example)](http://codepen.io/pawelgrzybek/pen/JNPKVE). Optionally slide a few items forward by passing `howManySlides` (number) argument [(example)](http://codepen.io/pawelgrzybek/pen/wdwWZQ). Optional `callback` (function) available as a third argument [(example)](http://codepen.io/pawelgrzybek/pen/JNPKQW).

**`goTo(index, callback)`**  
Go to an item at a particular `index` (number) [(example)](http://codepen.io/pawelgrzybek/pen/gWYLXP). Optional `callback` (function) available as a second argument [(example)](http://codepen.io/pawelgrzybek/pen/ZKzBvo).

**`remove(index, callback)`**  
Remove an item at a particular `index` (number) [(example)](http://codepen.io/pawelgrzybek/pen/BRBpQJ). Optional `callback` (function) available as a second argument [(example)](http://codepen.io/pawelgrzybek/pen/rmBjjE).

**`insert(item, index, callback)`**  
Insert new `item` (DOM element) at specific `index` (number) [(example)](http://codepen.io/pawelgrzybek/pen/QvLdaJ). Optional `callback` (function) available as a third argument [(example)](http://codepen.io/pawelgrzybek/pen/vmBgdZ).

**`prepend(item, callback)`**  
Prepend new `item` (DOM element) [(example)](http://codepen.io/pawelgrzybek/pen/rmBymW). Optional `callback` (function) available as a second argument [(example)](http://codepen.io/pawelgrzybek/pen/LyPWLe).

**`append(item, callback)`**  
Append a new `item` (DOM element) [(example)](http://codepen.io/pawelgrzybek/pen/RVbpZe). Optional `callback` (function) available as a second argument [(example)](http://codepen.io/pawelgrzybek/pen/rmByGj).

**`destroy(restoreMarkup = false, callback)`**  
Remove all event listeners on the instance [(example)](http://codepen.io/pawelgrzybek/pen/oWvZEd). Use `restoreMarkup` to restore the initial markup inside the selector [(example)](http://codepen.io/pawelgrzybek/pen/ZKzeoL). Optional `callback` (function) available as a third argument [(example)](http://codepen.io/pawelgrzybek/pen/Wjepyv).

**`currentSlide`**  
Prints current slide index [(example)](https://codepen.io/pawelgrzybek/pen/XRNOPP).

## Browser support

- IE10
- Chrome 12
- Firefox 16
- Opera 15
- Safari 5.1
- Android Browser 4.0
- iOS Safari 6.0

## Extra & Thanks

Thanks to [Paweł Grzybek](https://github.com/pawelgrzybek) for the original [Siema](https://github.com/pawelgrzybek/siema).

> Siema means 'hello' in Polish. When I play around with some code, I always use random names. That's the whole story behind the name of this one :)

Huge thanks to [Jarkko Sibenberg](http://www.sibenberg.com/) for the cute logo design! I can't thank [BrowserStack](https://www.browserstack.com) enough for giving me free access to their testing amazing service.
