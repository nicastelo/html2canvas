html2canvas-oklch
=================

#### JavaScript HTML renderer ####

`html2canvas-oklch` is a fork of [html2canvas](https://html2canvas.hertzen.com) that allows you to take "screenshots" of webpages (or parts thereof) directly in the user's browser. In addition to the original features, this fork adds support for the OKLCH color function.

### How does it work? ###
The script renders the current page as a canvas image, by reading the DOM and the different styles applied to the elements.

It does **not require any rendering from the server**, as the whole image is created on the **client's browser**. However, as it is heavily dependent on the browser, this library is *not suitable* to be used in nodejs.
It doesn't magically circumvent any browser content policy restrictions either, so rendering cross-origin content will require a [proxy](https://github.com/niklasvh/html2canvas/wiki/Proxies) to get the content to the [same origin](http://en.wikipedia.org/wiki/Same_origin_policy).

The script is still in a **very experimental state**, so I don't recommend using it in a production environment nor start building applications with it yet, as there will be still major changes made.

- **OKLCH Support:**
  This fork adds support for OKLCH color values, ensuring compatibility with Tailwind CSS 4 and other modern styling techniques.

### Browser compatibility ###

The library should work fine on the following browsers (with `Promise` polyfill):

* Firefox 3.5+
* Google Chrome
* Opera 12+
* IE9+
* Safari 6+

As each CSS property needs to be manually built to be supported, there are a number of properties that are not yet supported.

### Installation ###

Install the package using npm:

    $ npm install html2canvas-oklch

### Usage ###

```javascript
import html2canvas from 'html2canvas-oklch';

// or

const html2canvas = require('html2canvas-oklch');

html2canvas(document.body).then(function(canvas) {
    document.body.appendChild(canvas);
});
```

### Building ###

Clone git repository:

    $ git clone git://github.com/nicastelo/html2canvas.git

Install dependencies:

    $ npm install

Build browser bundle

    $ npm run build

### Examples ###

For more information and examples, please visit the [homepage](https://html2canvas.hertzen.com) or try the [test console](https://html2canvas.hertzen.com/tests/).

### Contributing ###

If you wish to contribute to the project, please send the pull requests to the main branch. Before submitting any changes, try and test that the changes work with all the support browsers. If some CSS property isn't supported or is incomplete, please create appropriate tests for it as well before submitting any code changes.

### License ###

This project is licensed under the MIT License. The fork retains the original license while incorporating additional modifications under the same terms.