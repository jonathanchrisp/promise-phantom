# Changes

## Version 3.1

**Date:** 18.04.2016 <br>
**Added:** Page.addLocalResource(options)<br>
**Added:** Page.removeLocalResource(name)<br>
**Added:** Page.getLocalResource(name)<br>
**Added:** Page.clearLocalResources()<br>
**Added:** Page.waitForLoad([timeout])<br>

Fixes #1

Prior to this version, if you had any local resources when you opened a HTML string or template using either `page.openHtml`, `page.renderHtml`, `page.openTemplate` or `page.renderTemplate`, these resources wouldn't be retrieved correctly when not using a specific rendering / opening directory. These changes allow you to add resources that you want to be retrievable by the webpage.

The `options` in `page.addLocalResource` is of type `{name: string, filename: string, content: buffer}` where `name` is a unique name, `filename` is the name of the file (where it should be stored in the temporary directory) and `content` is the buffer of the file.

A quick example (using co, for simplicity):

```javascript
let page = yield phantom.createPage();
let css  = 'body {background-color: #ccc;}';
let html = '' +
  '<html>' +
    '<head>' + 
      '<title>Title</title>' +
      '<link rel="stylesheet" href="css/my-css-file.css">' +
    '</head>' +
  '</html>';

let cssBuffer = new Buffer(css);

page.addLocalResource({
  name    : 'mycssfile',
  filename: 'css/my-css-file.css',
  content : cssBuffer
});

let status = yield page.openHtml(html);
```

The above webpage should now open the string and make a local request for the css file, which should be successful as temporary directory will look something like this (Unix-example):

```
/tmp/
 tmp-XXXXXXX/
   tmp-XXXXX.html
   css/
    my-css-file.css
 ...
```

All local resources are saved each time a new page is open and are deleted the moment the page has loaded.

`page.getLocalResource` will return the resource if it exists, `page.removeLocalResource` will remove one if it exist and return a boolean that indicates if anything has been removed. `page.clearLocalResources` will remove all local resources.

## Version 3.0

**Date:** 27.12.2015<br>
**Changed**: Page.renderPdf()<br>
**Changed**: Page.renderHtml(htmlString, renderDirectory)<br>
**Changed**: Page.renderTemplate(template, renderDirectory, option)<br>

Due to an issue that sometimes caused the Pdf to be rendered blank, the above mentioned functions has been changed from returning a `string` to a `buffer`.

When using `buffer.toString()` some of the data seems get lost and the rendered PDF was therefore blank.

Due to a breaking change, the version has gone from 2.1 to 3.0.

## Version 2.1

**Date:** 26.12.2015 <br>
**Added:** Page.openHtml(htmlString, renderDirectory)<br>
**Added:** Page.openTemplate(template, renderDirectory, options)<br>
**Changed:** Page.renderTemplate(template, renderDirectory, options)<br>
**Changed:** Page.renderHtml(htmlString, renderDirectory)<br>
**Changed:** Phantom.addCookie(cookie)

`Page.openHtml(htmlString, renderDirectory)` works much like `Page.open(location)` but instead of requiring an address, it uses a HTML string. This is done by either saving it to a file with a pseudo-unique name in the renderDirectory specified, or in the operating systems temporary folder, if renderDirectory is omitted. It is then loaded using `Page.open` before the file is deleted.

`Page.openTemplate(template, renderDirectory, options)` works exactly as above, but with a template object that has a `.render` function that returns a HTML string.

`Page.renderTemplate(template, renderDirectory, options)` has been changed to use `Page.openTemplate` and therefore works without specifying a renderDirectory.

`Page.renderHtml(htmlString, renderDirectory)` has been changed to use `Page.openHtml`. Same changes as above.

It should be noted that if you have any includes (i.e. script src="some-javascript-file.js") that are local files, you should still use a renderDirectory as PhantomJS will try to find these files relative to the render directory.

`Phantom.addCookie(cookie)` now has type checking, which will throw TypeError on invalid cookies. It is expected to be an object, with a name as well as a value

As with minor versions, none of the changes should be breaking changes and everything should be working as they did in 2.0

## Version 2.0

**Date:** 19.12.2015 <br>
**Added:** Page <br>
**Added:** Phantom <br>
**Changed:** Too much to specify

Major rewrite of the entire library and now uses node-phantom-simple instead. All functions that PhantomJS include are documented with their documentation. All functions are documented, except for a few which lacks documentation from the creators of PhantomJS.

In addition, this version was also pushed to NPM.

## Version 1.0

**Date:** 17.11.2015<br>

Uses phantomjs-node as the wrapper around PhantomJS.
